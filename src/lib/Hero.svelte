<div id="hero" class="wrapper">
  <div>
    <h1>Hi, I'm Daniel Chapman</h1>
    <p>Let's talk frontend!</p>
  </div>
</div>

<style lang="scss">
  .wrapper {
    padding-left: 1.5rem;
    padding-right: 1.5rem;
    display: flex;
    flex-direction: column;
    > div {
      border-left: 1px solid white;
      border-right: 1px solid white;
      padding-left: inherit;
      padding-right: inherit;
      &:first-child {
        padding-top: 1rem;
      }
      &:last-child {
        padding-bottom: 1rem;
      } 
    }
  }
</style>