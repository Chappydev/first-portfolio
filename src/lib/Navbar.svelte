<nav>
  <a href="#about-me">About Me</a>
  <a href="#projects">Projects</a>
  <a href="#skills">Skills</a>
  <a href="#contact">Contact</a>
</nav>

<style lang="scss">
  @use './partials/variables' as v;

  nav {
    position: fixed;
    top: 0;
    height: v.$navbar-height;
    padding: 0.5rem;
    background-color: #101010;
    display: flex;
    justify-content: space-around;
    align-items: center;
    width: 100%;
    z-index: 1000;
  }
</style>