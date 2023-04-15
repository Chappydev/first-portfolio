<script>
  export let project;

  let viewportHeight;
  let imgElement;
  let imgPosition;
  $: inView = imgPosition !== undefined && imgPosition < viewportHeight;

  const setImgPosition = () => {
    imgPosition = imgElement?.getBoundingClientRect()?.y;
  }

</script>

<svelte:window bind:innerHeight={viewportHeight} 
  on:resize={setImgPosition}
  on:scroll={setImgPosition}
/>

<div class="wrapper">

  <h3>{project.name}</h3>

  <img class:fly-in={inView} bind:this={imgElement} src={project.img} alt={`Screenshot of the ${project.name} project`}>

  <div class="inner-wrapper description">
  <h4>Description</h4>
  <p>{project.description}</p>
  </div>
  
  <div class="inner-wrapper challenges">
    <h4>Challenges</h4>
    <ul>
      {#each project.challenges as challenge}
        <li>{challenge}</li>
      {/each}
    </ul>
  </div>

  <div class="buttons"><a href={project.link} target="_blank" rel="noreferrer">Try It</a><a href={project.github} target="_blank" rel="noreferrer">Code</a></div>
</div>

<style lang="scss">
  @use 'partials/mixins' as m;
  @use 'partials/variables' as v;

  .wrapper {
    padding: 0 v.$outer-padding;
    margin-top: 4rem;
    @include m.for-size(s-down) {
      @include m.max-width;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 1rem;
    }
    @include m.for-size(m-up) {
      display: grid;
      grid-template-columns: minmax(200px, 600px) minmax(200px, 600px);
      gap: 1.5rem 2.5rem;
      justify-content: center;
      justify-items: center;
      align-items: center;
    }
  }

  img {
    $transition-time: 900ms;
    aspect-ratio: 3 / 2;
    object-fit: cover;
    width: min(90%, 350px);
    border-radius: 0.8rem;
    position: relative;
    left: -800px;
    opacity: 0;
    transition: opacity $transition-time ease-out 0s, left $transition-time ease-out 0s;

    &.fly-in {
      left: 0px;
      opacity: 1;
    }
  }

  p {
    text-align: left;
  }

  .inner-wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
  }

  ul {
    list-style: disc;
    padding-inline-start: 25px;
  }

  .buttons {
    display: flex;
    justify-content: space-evenly;

    a {
      padding: 0.5em 1.2em;
      border-radius: 30% / 50%;
      border: 2px solid orange;
      color: white;
      text-decoration: none;
    }
  }

  @include m.for-size(m-up) {
    h3 {
      grid-column: 1 / 3;
    }

    img {
      grid-row: 2 / 4;
    }

    .challenges {
      grid-column: 2 / 3;
    }

    .buttons {
      grid-column: 1 / 3;
      justify-self: stretch;
    }
  }

  @include m.for-size(s-down) {
    .buttons {
      align-self: stretch;
    }
  }
</style>