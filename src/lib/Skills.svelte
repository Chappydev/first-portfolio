<section id="skills">
  <div>
    <h2>I'm <span class="colored-orange">good</span> at these</h2>
    <ul>
      <li>HTML</li>
      <li>CSS</li>
      <li>Javascript</li>
      <li>React</li>
    </ul>
  </div>
  <div>
    <h2>I'm <span class="colored-orange">learning</span> these</h2>
    <ul>
      <li>SQL</li>
      <li>MongoDB</li>
      <li>Svelte</li>
      <li>Express</li>
      <li>NodeJS</li>
    </ul>
  </div>
</section>

<style lang="scss">
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

  .colored-orange {
    color: orange;
  }

  div:has(ul) {
    display: flex;
    flex-direction: column;
    align-items: center;
    &:first-of-type {
      position: relative;
      padding-bottom: 2rem;
      &::after {
        content: '';
        position: absolute;
        width: 70%;
        height: 1px;
        bottom: 0;
        background-color: white;
      }
    }
    &:not(:first-of-type) {
      margin-top: 2rem;
    }
    ul {
      // TODO: fix the text bubbles getting stretched out on
      //       larger screens
      list-style: none;
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 0.5em;
      width: 90%;
      li {
        text-align: center;
        padding: 0.4em;
        border-radius: 25% / 50%;
        border: 2px solid orange;
      }
    }
  }
</style>