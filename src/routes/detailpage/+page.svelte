    <header>
        <a href="/"><h1>qatar museums</h1></a>
    </header>
    <div class="detail">
      <h2>Mona Lisa</h2>
      <img src="/mona.jpg">
    </div>  
  <style>

    body {
      margin: 0;
    }
     header {
        background:repeating-linear-gradient(
            45deg,
            var(--gold),
            var(--gold) 1px,
            var(--rose)10px,
            var(--rose) 20px
            );
        display: flex;
        align-items: center;
        justify-content: center;
        line-height: 20px;
        border-bottom: 1px solid var(--black);
        width: 100%;
        height: 3.7em;
        z-index: 33;
    }

	a {
		text-decoration: none;
    height: max-content;
	}

  header a:hover h1 {
	font-size: 3.2em;
  }

  h1, h2 {
    margin-left: 0.5rem;
    font-size: 3em;
    font-weight: 100;
    color: var(--black);
  }

  h2 {
    font-size: 2.5em;
    padding: 1em;
    backdrop-filter: blur(4px);
  }

  div {
    align-items: center;
    display: flex;
    flex-direction: column;
    height: 100vh;
    background: var(--rose);
      background-image: radial-gradient(var(--gold) 40%, transparent 0%);
      background-size: 35px 35px;
    }

  img {
    width: 20em;
    border-radius: 8px;

  }

  </style>