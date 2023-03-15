<script>
  import AboutMe from "./lib/AboutMe.svelte";
  import Contact from "./lib/Contact.svelte";
  import Hero from "./lib/Hero.svelte";
  import Navbar from "./lib/Navbar.svelte";
  import Projects from "./lib/Projects.svelte";
  import Skills from "./lib/Skills.svelte";

</script>

<div id="intro-section">
  <Navbar />

  <Hero />
</div>

<AboutMe/>

<Skills/>

<Projects />

<Contact />

<style lang="scss">
  #intro-section {
    height: 100vh;
    display: grid;
    grid-template-rows: auto 1fr;
  }
</style>