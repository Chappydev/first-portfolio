<script>
  
</script>

<section id="about-me">
  <div class="wrapper">
    <h2>So what's this guy's deal?</h2>
  </div>
  <div class="wrapper">
    <p>
      I am first and foremost a passionate learner. For as long as I can remember, 
      from practicing yo-yo tricks to teaching myself Japanese, 
      I've always loved the challenge of learning a new skill.
    </p>
    <p>
      Right now, I am passionate about the web, and am determined 
      to become the best developer I can be. I am confident that my
      skills with both frontend and backend technologies, and more importantly,
      my ability to quickly pick up new skills when the need arises, make me a strong 
      addition to any developer team.
    </p>
  </div>
</section>

<style lang="scss">
  @use './partials/mixins.scss' as m;
  @use './partials/variables' as v;

  .wrapper {
    flex: 1 0 0;
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

    @include m.for-size(s-down) {
      @include m.line-spacer;  
    }

    @include m.for-size(m-up) {
      padding: v.$outer-padding;
    }

    &:first-of-type {
      @include m.for-size(m-up) {
        justify-content: center;
        border-right: 1px solid white;
      }
    }
  }


  section {
    display: flex;
    flex-direction: column;

    @include m.for-size(m-up) {
      margin-top: 0;
      padding-bottom: 0;
      flex-direction: row;
    }
  
    h2 {
      text-align: center;
    }
  }
</style>