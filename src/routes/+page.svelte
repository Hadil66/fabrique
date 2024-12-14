<script>
  export let data;

  let filterText = "";
  
  import Search from "$lib/Search.svelte";
  import Searchbar from "$lib/molecules/searchbar.svelte";

  function handleScroll() {
    if (scrollContainer.scrollLeft >= scrollContainer.scrollWidth / 2) {
      scrollContainer.scrollLeft -= scrollContainer.scrollWidth / 2;
    }
  }

  import { activeFilter } from "$lib/store";
  import Filters from "$lib/molecules/Filters.svelte";

  const techniques = ["Pottery", "Islamic art", "Tapestry", "Glass"];
</script>

<header>
  <a href="/page2"><h1>qatar museums</h1></a>
</header>

<div class="scroll-container">
  <ul class="masonry">
    {#each data.artObjects as art, index}
      <li
        class="masonry-item"
        class:hidden={$activeFilter !== "*" && $activeFilter !== techniques[index % techniques.length]}
        data-category={techniques[index % techniques.length]}
      >
        <figure>
          <figcaption class="caption-{index % 5}"></figcaption>
        </figure>
      </li>
    {/each}
  </ul>
</div>

<div>
  <Searchbar />
  <Filters />
</div>

<style>
  header {
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

  .scroll-container {
    display: flex;
    overflow-x: auto;
    scroll-snap-type: x mandatory;
	margin: 5vh 0 0 0;
  }

  .masonry {
	background: var(--rose);
	background-image: radial-gradient(#ff78dfff 40%, transparent 0);
	background-size: 35px 35px;
    column-count: 2;
    column-gap: 0;
    list-style: none;
    padding: 0;
  }

  .caption-0,
  .caption-1,
  .caption-2,
  .caption-3,
  .caption-4 {
    background-blend-mode: multiply;
    background-image: url(/mona.jpg);
    background-position: center;
    background-size: cover;
  }

  .caption-0 {
    background-color: var(--rose);
  }

  .caption-1 {
    background-color: var(--rose-pink);
  }

  .caption-2 {
    background-color: var(--gold);
  }

  .caption-3 {
    background-color: var(--persian-blue);
  }

  .caption-4 {
    background-color: var(--argentinian-blue);
  }

  /* DIT AANPASSEN VOOR DE ACTIVE FILTER */
  .masonry-item.hidden {
    filter: opacity(0);
    pointer-events: none;
    transition: 1s;
	
  }

  figure {
    margin: 0;
  }

  figcaption {
    width: 22em;
    height: 28em;
  }

  @media (min-width: 600px) {
    .masonry {
      column-count: 1;
    }
  }

  @media (min-width: 900px) {
    .masonry {
      column-count: 4;
    }
  }
</style>
