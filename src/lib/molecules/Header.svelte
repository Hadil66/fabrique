<header>
  <h1>Qatar Museums</h1>
  <div class="drip">
    <div class="big-drip"></div>
    <div id="ric-flair-drip"></div>
    <div id="drip-too-hard"></div>
    <div id="drip-or-drown"></div>
  </div>
</header>

<style>
  header {
    align-items: center;
    animation: headie-one;
    animation-timeline: scroll();
    animation-range: 0vh 90vh;
    background-color: #c60000;
    display: flex;
    flex-direction: column;
    justify-content: center;
    position: fixed;
    top: 0;
    width: 100%;
    z-index: 369;
  }

  h1 {
    color: white;
    font-family: "SuperWoobly";
    text-align: center;
    text-transform: uppercase;
  }

  @keyframes headie-one {
    from {
      background-position: 50% 0;
      height: 100vh;
      font-size: 2.5em;
    }
    to {
      background-position: 50% 100%;
      height: 10vh;
      font-size: 1em;
    }
  }

  .drip {
    display: flex;
    flex-direction: row;
    position: absolute;
    bottom: 0;
    right: 0;
    width: 5em;
    border-radius: 8px;
  }

  .drip div {
    width: 1.3em;
    height: 5em;
    border-radius: 30px;
  }

  #ric-flair-drip, #drip-too-hard, #drip-or-drown {
    background: #c60000;
    position: absolute;
  }

  #ric-flair-drip {
    top: 2.6em;
    left: 0em;
  }

  #drip-too-hard {
    top: 1.2em;
    left: 1.7em;
  }

  #drip-or-drown {
    top: 2em;
    left: 3.4em;
  }
</style>
