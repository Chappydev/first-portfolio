<script>
  import { onMount } from "svelte";

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

  <p>{project.description}</p>
  
  <h4>Challenges</h4>
  <ul>
    {#each project.challenges as challenge}
      <li>{challenge}</li>
    {/each}
  </ul>

  <div class="buttons"><a href={project.link} target="_blank" rel="noreferrer">Try It</a><a href={project.github} target="_blank" rel="noreferrer">Code</a></div>
</div>

<style lang="scss">
  @use 'partials/mixins' as m;
  @use 'partials/variables' as v;

  .wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 1rem;
    padding: 0 v.$outer-padding;
    margin-top: 2rem;
    @include m.max-width;

  }

  img {
    $transition-time: 900ms;
    aspect-ratio: 3 / 2;
    object-fit: cover;
    width: min(90%, 350px);
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

  ul {
    list-style: disc;
    padding-inline-start: 25px;
  }

  .buttons {
    display: flex;
    justify-content: space-evenly;
    align-self: stretch;

    a {
      padding: 0.5em 1.2em;
      border-radius: 30% / 50%;
      border: 2px solid orange;
      color: white;
      text-decoration: none;
    }
  }

</style>