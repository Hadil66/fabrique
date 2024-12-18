<script>
  export let data;
</script>

<div class="book">
  <div class="cover">
    <div class="cover-text">
      <h1>qatar museums</h1>
	  <svg viewBox="0 0 500 500">
		<path id="curve" d="M73.2,148.6c4-6.1,65.5-96.8,178.6-95.6c111.3,1.2,170.8,90.3,175.1,97" fill="none" />
		<text width="500">
		  <textPath xlink:href="#curve">
			A Christmas Carol
		  </textPath>
		</text>
	  </svg>    
	</div>
    <div class="back-cover"></div>
  </div>
  <div class="page">
    <div class="page-content">
      <ul class="masonry">
        {#each data.artObjects as art, index}
          <li>
            <figure>
              <img
                src={"https://fdnd-agency.directus.app/assets/" + art.image}
                alt={art.title}
                height={art.height}
                width={art.width}
                loading="lazy"
              />
              <figcaption>
                <h2>{art.title}</h2>
              </figcaption>
            </figure>
          </li>
        {/each}
      </ul>
    </div>
  </div>
  <div class="side"></div>
  <div class="bottom"></div>
  <div class="shadow"></div>
</div>

<style>
  .book {
    transform-style: preserve-3d;
    transform: rotateX(45deg) rotateY(0deg) rotateZ(-45deg);
    transition: transform 1s;
    position: relative;
    width: max-content;
    height: 40em;
	margin: 5em;
  }

  .book .side {
    width: 3em;
    height: 40em;
    background-image: url(/cover.png);
    position: absolute;
    left: -3em;
    top: 0;
    transform-origin: 100% 100%;
    transform: rotateY(-90deg) rotateX(0deg);
  }

  .book .bottom {
    width: 25em;
    height: 3em;
    background: var(--eggshell);
    position: absolute;
    bottom: 0;
    left: 0;
    transform-origin: 100% 100%;
    transform: rotateX(90deg);
  }

  .book .shadow {
    background: transparent;
    transform: translateZ(-3em);
    box-shadow: -1em 1em 0px 0px var(--eerie-black);
    z-index: 1;
    width: 25em;
    height: 40em;
    position: absolute;
    top: 0;
    left: 0;
  }

  .book .cover {
    background-image: url(/cover.png);
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    height: 40em;
    left: 0;
    position: absolute;
    top: 0;
    transition:
    transform 1s,
	box-shadow 0.5s 0.2s;
    transform-origin: 0 50%;
    transform-style: preserve-3d;
    width: 25em;
    z-index: 8;
  }

  .book .cover.open {
    box-shadow: 2.2em 1em 0px 0px var(--eerie-black);
    transform: rotateX(0deg) rotateY(-180deg) rotateZ(0deg);
  }

  .book .cover-text {
  padding: 1em;
  position: absolute;
  z-index: 2;
}

h1, svg {
  position: absolute;
  text-transform: capitalize;
}

h1 {
  font-size: 1.5em;
  top: 1.5em;
  left: 5.2em;
  color: var(--eggshell);
  letter-spacing: 1px;
  width: max-content;
}

svg  {
  z-index: 15;
  top: 2em;
  left: 2em;
  width: 100%;
  height: auto;
}

svg textPath {
	  fill: var(--eggshell);
	  font-size: 2em;
}

  .book .back-cover {
    background: var(--burgundy);
    width: 100%;
    height: 100%;
    position: absolute;
    z-index: 1;
    transform: translateZ(-0.4px);
  }

  .book .page {
    width: 25em;
    height: 40em;
    position: absolute;
    top: 0;
    left: 0;
    transform-origin: 0 50%;
    transform-style: preserve-3d;
    transition:
    transform 1s,
    box-shadow 0.5s 0.2s;
    z-index: 7;
  }

  .book .page-content {
    background-image: url(/background1.jpg);
    width: 100%;
    height: 100%;
    overflow: hidden;
    position: absolute;
  }

  .book.open {
    transform: rotateX(35deg) rotateY(0deg) rotateZ(-35deg);
  }

  ul {
    margin: 0;
    padding: 0;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    padding: 2em;
  }
  li {
    background-image: url(/content.jpg);
    background-position: center;
    height: 10em;
    list-style-type: "";
    width: 8em;
    background-repeat: no-repeat;
  }
</style>
