<script>
  
</script>

<section id="about-me">
  <div class="wrapper">
    <h2>So what's this guy's deal?</h2>
  </div>
  <div class="wrapper">
    <p>
      I am a passionate learner. For as long as I can remember, 
      from practicing yo-yo tricks to teaching myself Japanese, 
      I've always loved learning new things and developing new skills.
    </p>
    <p>
      Right now, I am passionate about the web, and am determined 
      to become the best developer I can be. I am confident that my
      skills with frontend and backend technologies, and more importantly,
      my ability to quickly pick up new skills, would make me a strong 
      addition to any developer team.
    </p>
  </div>
</section>

<style lang="scss">
  @use './partials/mixins.scss' as m;
  @use './partials/variables' as v;

  .wrapper {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 0 v.$outer-padding;

    p {
      @include m.max-width;
    }

    > p:not(:first-child) {
      margin-top: 1.5em;
    }

    @include m.line-spacer;  
  }

  section {
    display: flex;
    flex-direction: column;
  
    h2 {
      text-align: center;
    }
  }
</style>