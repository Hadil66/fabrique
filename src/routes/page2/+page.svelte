    <header>
        <a href="/page2"><h1>qatar museums</h1></a>
    </header>
    <img src="/mona.jpg">
  
  <style>
     header {
        animation: headie-one;
        animation-timeline: scroll();
        animation-range: 0vh 90vh;
        background:repeating-linear-gradient(
            45deg,
            var(--argentinian-blue),
            var(--argentinian-blue) 10px,
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
        position: fixed;
        top: 0;
        z-index: 33;
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

	a {
		text-decoration: none;
	}

  header a:hover h1 {
	font-size: 3.2em;
  }

  h1 {
    margin-left: 0.5rem;
    font-size: 3em;
    font-weight: 100;
    color: var(--black);
    transition: 0.3s ease-in;
  }

  </style>