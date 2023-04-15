<script>
  import Skill from "./Skill.svelte";


  const goodSkills = [
    {name: 'HTML'},
    {name: 'CSS'},
    {name: 'SASS'},
    {name: 'Javascript'},
    {name: 'React'},
  ];

  const otherSkills = [
    {name: 'Next.js'},
    {name: 'SQL'},
    {name: 'MongoDB'},
    {name: 'Svelte'},
    {name: 'NodeJS'},
    {name: 'Express'},
  ]
</script>

<section id="skills">
  <div>
    <h2>I'm <span class="orange">good</span> at these</h2>
    <ul>
      {#each goodSkills as skill }
        <li><Skill {skill}/></li> 
      {/each}
    </ul>
  </div>
  <div>
    <h2>I'm <span class="orange">learning</span> these</h2>
    <ul>
      {#each otherSkills as skill }
        <li><Skill {skill}/></li> 
      {/each}
    </ul>
  </div>
</section>

<style lang="scss">
  @use './partials/mixins' as m;
  @use './partials/variables' as v;

  // TODO: make responsive
  //       - make line a simple border that fills the full height
  section {
    display: flex;
    flex-direction: column;

    @include m.for-size(m-up) {
      margin-top: 0;
      padding-bottom: 0;
      > div {
        flex: 1 0 0;
      }
      flex-direction: row;
    }
  }

  section:first-child {
    border-bottom: 1px solid white;
  }

  h2 {
    text-align: center;
    margin-bottom: 1.5rem;
  }

  div:has(ul) {
    display: flex;
    flex-direction: column;
    align-items: center;
    @include m.for-size(s-down) {
      @include m.line-spacer;  
    }

    @include m.for-size(m-up) {
      padding: v.$outer-padding;
    }

    &:first-of-type {
      @include m.for-size(m-up) {
        border-right: 1px solid white;
      }
    }
    // &:first-of-type {
    //   position: relative;
    //   padding-bottom: 2rem;
    //   &::after {
    //     content: '';
    //     position: absolute;
    //     width: 70%;
    //     height: 1px;
    //     bottom: 0;
    //     background-color: white;
    //   }
    // }
    // &:not(:first-of-type) {
    //   margin-top: 2rem;
    // }
    > * {
      @include m.max-width;
    }
    ul {
      list-style: none;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 0.5em;
      width: 90%;
      justify-items: center;
      li {
        width: clamp(90px, 90%, 125px);
      }
    }
  }
</style>