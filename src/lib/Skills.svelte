<script>
  import Skill from "./Skill.svelte";


  const goodSkills = [
    {name: 'HTML'},
    {name: 'CSS'},
    {name: 'Javascript'},
    {name: 'React'},
  ];

  const otherSkills = [
    {name: 'SQL'},
    {name: 'MongoDB'},
    {name: 'Svelte'},
    {name: 'Express'},
    {name: 'NodeJS'},
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
  @use './partials/mixins.scss' as m;

  // TODO: make responsive
  //       - make line a simple border that fills the full height
  section {
    display: flex;
    flex-direction: column;
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
    @include m.line-spacer;
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
    ul {
      // TODO: fix the text bubbles getting stretched out on
      //       larger screens
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