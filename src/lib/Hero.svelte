<div id="hero" class="wrapper">
  <div>
    <div>
      <h1>Hi, I'm <span class="orange">Daniel Chapman</span></h1>
      <p>Let's talk frontend!</p>
    </div>
    <div id="fancy-text">
      <div class="right">VIM Motions</div>
      <div class="left">勉強は楽しい</div>
      <div class="right">効率的な勉強法</div>
      <div class="left">learnToCode()</div>
      <div class="right">Let's try this</div>
      <div class="left">ウェブ開発</div>
    </div>
  </div>
</div>

<style lang="scss">
  @use './partials/mixins' as m;

  .wrapper {
    height: 100vh;
    padding-left: 1.5rem;
    padding-right: 1.5rem;
    > div {
      height: 100%;
      border-left: 1px solid white;
      border-right: 1px solid white;
      padding-left: inherit;
      padding-right: inherit;
      display: flex;
      align-items: center;
      justify-content: space-evenly;

      &:first-child {
        padding-top: 1rem;
      }
      &:last-child {
        padding-bottom: 1rem;
      } 

      h1 {
        margin-bottom: 0.4em;
      }
    }
  }

  #fancy-text {
    max-width: 400px;
    display: grid;
    grid-template-columns: 1fr 1fr;
    grid-template-rows: 20px 20px;
    align-items: center;
    perspective: 150px;

    > div {
      $rotateY: 65deg;
      $rotateX: 10deg;
      position: relative;
      font-size: 1rem;
      white-space: nowrap;
      
      &:nth-child(odd) {
        right: -10px;
        transform-origin: 80% 50%;
        transform: rotateY($rotateY); 
        opacity: 0.6;
      }

      &:nth-child(even) {
        left: -10px;
        transform-origin: 20% 50%;
        transform: rotateY(-$rotateY); 
        opacity: 0.6;
      }

      &:nth-child(1) {
        align-self: self-end;
        transform: rotateY($rotateY) rotateX(-$rotateX);
      }

      &:nth-child(2) {
        align-self: self-end;
        transform: rotateY(-$rotateY) rotateX(-$rotateX);
      }

      &:nth-child(3) {
        right: -5px;
      }

      &:nth-child(4) {
        left: -5px;
      }

      &:nth-child(5) {
        align-self: self-start;
        transform: rotateY($rotateY) rotateX($rotateX);
      }

      &:nth-child(6) {
        align-self: self-start;
        transform: rotateY(-$rotateY) rotateX($rotateX);
      }

    }
  }

  .right {
    text-align: right;
  }
  .left {
    text-align: left;
  }

  @include m.for-size(s-down) {
    .wrapper > div {
      flex-direction: column;
      justify-content: center;
      gap: 4rem;
    }
  }
</style>
