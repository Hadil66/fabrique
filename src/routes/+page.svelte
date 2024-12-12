<script>
	export let data;
	console.log(data); 

	import Search from '$lib/Search.svelte'; 
	let filterText = '';
    
	import Searchbar from '$lib/molecules/searchbar.svelte';

	let scrollContainer; 

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
    <h1> qatar museums</h1>
</header>

<div class="scroll-container"
bind:this={scrollContainer}
  on:scroll={handleScroll}>
  <ul class="masonry">
	{#each data.artObjects as art, index}
	  <li
		class="masonry-item"
		class:hidden={$activeFilter !== "*" &&
		  $activeFilter !== techniques[index % techniques.length]}
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
	<Searchbar/>
   <Filters />
</div>

<style>
	header {
		display: flex;
		align-items: center; 
		justify-content: center;
		line-height: 20px;
		border-bottom: 1px solid var(--black);
		width: 100%;
		height: 3.7em;
		position: fixed;
		z-index: 33;
		background: var(--argentinian-blue);
		top: 0;
	}

	h1 {
		margin-left: 0.5rem;    
		font-size: 3em;  
		font-weight: 100;
		color: var(--black);
	}

	.scroll-container {
		display: flex;
		overflow-x: auto;
		scroll-snap-type: x mandatory;
	}

	.masonry {
		column-count: 2;
		column-gap: 0;
		list-style: none;
		padding: 0;
	}

	.masonry-item {
		break-inside: avoid;
		display: block;
		background-color: var(--white);
		box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
		position: relative;
		overflow: hidden;
		transition: opacity 0.3s;
	}

	.caption-0 { 		
		background-image: url(/mona.jpg);
		background-color: var(--rose);
		background-blend-mode: multiply;
		background-size: cover; 
		background-position: center;
}

	.caption-1 { 		
		background-image: url(/mona.jpg);
		background-color: var(--rose-pink); 
		background-blend-mode: multiply; 
		background-size: cover; 
		background-position: center;
	}

	.caption-2 { 		
		background-image: url(/mona.jpg);
		background-color: var(--gold); 
		background-blend-mode: multiply; 
		background-size: cover; 
		background-position: center;
	}

	.caption-3 { 		
		background-image: url(/mona.jpg);
		background-color: var(--persian-blue); 
		background-blend-mode: multiply; 
		background-size: cover; 
		background-position: center;
	}

	.caption-4 { 		
		background-image: url(/mona.jpg);
		background-color: var(--argentinian-blue);
		background-blend-mode: multiply; 
		background-size: cover; 
		background-position: center;
	}


	.masonry-item.hidden {
		filter: opacity(0.3);
		pointer-events: none;
		transition: 1s;
	}

	.masonry-item:focus {
		outline: 2px solid var(--black);
		outline-offset: 3px;
	}

	figure {
		margin: 0;
		position: relative;
	}

	figcaption {
		width: 22em;
		height: 28em;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		transition: opacity 0.3s ease-in-out;
	}

	figcaption:nth-of-type(4n){
		background-color: var(--rose);
	}

	/* Responsiee layout */
	@media (min-width: 600px) {
		.masonry {
			column-count: 1;
		}
	}

	@media (min-width: 900px) {
		.masonry {
			column-count: 4;
		}
		h2 {
			font-size: 1.5rem;
		}
	}

	/* Prefers reduced motion */
	@media (prefers-reduced-motion) {
		.masonry-item {
			transition: none;
		}

		img {
			transition: none;
		}
	}
</style>