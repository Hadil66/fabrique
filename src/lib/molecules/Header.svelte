<header>
  <h1>Qatar Museums</h1>
  <div class="drip">
    <div class="big-drip"></div>
    <div id="ric-flair-drip"></div>
    <div id="drip-too-hard"></div>
    <div id="drip-or-drown"></div>
  </div>

  <svg viewBox="0 0 24 24" width="30" height="30">
    <polygon class="droplet" points="3.3 4.06 0 13.72 1.86 18.5 7.93 21.59 14.11 18.92 15.79 13.72 12.33 3.7 7.89 0 3.3 4.06"></polygon>
  </svg>
  <svg viewBox="0 0 24 24" width="30" height="30">
    <polygon class="droplet" points="3.3 4.06 0 13.72 1.86 18.5 7.93 21.59 14.11 18.92 15.79 13.72 12.33 3.7 7.89 0 3.3 4.06"></polygon>
  </svg>

</header>

<style>
  header {
    align-items: center;
    animation: headie-one;
    animation-timeline: scroll();
    animation-range: 0vh 90vh;
    background-color: lch(37 90.45 43.27);
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
    margin: 0;
    text-align: center;
    text-transform: uppercase;
  }

  @keyframes headie-one {
    0% {
      background-position: 50% 0;
      height: 100vh;
      font-size: 2.5em;
    }
    100% {
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
    background: lch(37 90.45 43.27);
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

  svg { 
    animation: droplet 14s ease-in-out infinite;
    position: absolute;
    top: 3em;
    right: -0.2em;
  }
   svg:nth-of-type(2) {
    animation-delay: 0.5s;
    position: absolute;
    top: 3em;
    right: 3.1em;
  }

  .droplet {
    fill: lch(37 90.45 43.27);
  }

@keyframes droplet {
    0% {
      transform: translateY(0); 
      opacity: 1;
    }
    40% {
      transform: translateY(100vh); 
      opacity: 0.5; 
    }
    100% {
      transform: translateY(100vh); 
      opacity: 0; 
    }
  }
</style>
