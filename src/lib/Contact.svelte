<script>
  import Icon from '@iconify/svelte';

  const iconDimensions = 30;
</script>

<section id="contact">
  <header>
    <h2>Contact</h2>
    <h3>Let's <span class="orange">talk</span>!</h3>
  </header>
  <address>
    <div class="contact-links">
      Email: 
      <a href="mailto:danjtchapman@gmail.com">danjtchapman@gmail.com</a>
    </div>
    <div class="contact-icons">
      <a href="https://www.linkedin.com/in/danjtchapman" target="_blank" rel="noreferrer">
        <Icon width={iconDimensions} height={iconDimensions} icon="uil:linkedin-alt" />
      </a>
      <a href="https://github.com/Chappydev" target="_blank" rel="noreferrer">
        <Icon width={iconDimensions} height={iconDimensions} icon="uil:github-alt" />
      </a>
    </div>
  </address>
</section>

<style lang="scss">
  @use './partials/mixins' as m;

  section {
    > * {
      padding: 0 1rem;
    }

    padding-bottom: 1rem;
  }

  header,
  address {
    display: flex;
    flex-direction: column;
    align-items: center;
  }

  address {
    > div {
      &:first-of-type {
        margin-top: 1rem;
      }

      margin-top: 0.5rem;
    }
  }

  @include m.for-size(m-up) {
    address {
      flex-direction: row;
      > div {
        flex: 1 0 0;
        display: flex;
        justify-content: center;
        gap: 0.6em;
      }
    }
  }
</style>