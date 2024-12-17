<script>
	export let data;
	console.log(data); // Hiermee kun je zien hoe de API-respons eruitziet

	import Search from '$lib/Search.svelte'; // Icoon wordt gebruikt voor de searchbar
	let filterText = '';
    
	import Navbar from '$lib/Navbar.svelte';

	import Searchbar from '$lib/molecules/searchbar.svelte';

	let scrollContainer; // variable scroll container. 

function handleScroll() {
  // Als de gebruiker halverwege de scrollcontainer is gescrolld...
  if (scrollContainer.scrollLeft >= scrollContainer.scrollWidth / 2) { 
    // ... scroll dan terug naar het begin van de tweede helft van de inhoud.
    scrollContainer.scrollLeft -= scrollContainer.scrollWidth / 2;
  }
}
  
import { activeFilter } from "$lib/store";
	import Filters from "$lib/molecules/Filters.svelte";
  
	const techniques = ["Pottery", "Islamic art", "Tapestry", "Glass"];
  </script>

<Navbar />
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
		  <picture>
			<source
			  srcset={"https://fdnd-agency.directus.app/assets/" +
				art.image +
				".avif"}
			  type="image/avif"
			/>
			<source
			  srcset={"https://fdnd-agency.directus.app/assets/" +
				art.image +
				".webp"}
			  type="image/webp"
			/>
			<div class="image-container">
				<div class="strikje"><img src="strikje.svg" width="130" height="130" alt=""></div>
			<img
			  src={"https://fdnd-agency.directus.app/assets/" + art.image}
			  alt={art.title}
			  height={art.height}
			  width={art.width}
			  loading="lazy"
			/></div>
		  </picture>
		  <figcaption>
			<h2>{art.title}</h2>
		  </figcaption>
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
	.scroll-container {
		display: flex;
		overflow-x: auto;
		overflow-y: visible;
		padding:  4rem;
		scroll-snap-type: x mandatory;
		background-color: #000000;

	}

	.masonry {
		column-count: 1;
		column-gap: 2rem;
		list-style: none;
		padding: 0;
		margin-top: 3rem;

	}

	.masonry-item {
		break-inside: avoid;
		display: block;
		background-color: #fff;
		border-radius: 50%;
		box-shadow: 4px 4px 6px rgba(0, 0, 0, 0.1);
		margin: 2rem 2rem 2rem 2rem;

		position: relative;
		
	}

	.masonry-item.hidden {
		filter: opacity(0.3);
		pointer-events: none;
		transition: 1s;
	
		
	}

	.masonry-item:focus {
		outline: 2px solid #020202;
		outline-offset: 3px;
	
	}

	.masonry-item:hover img,
	.masonry-item:focus img {
		transform: scale(1);
	}

	.masonry-item:hover figcaption,
	.masonry-item:focus figcaption {
		opacity: 1;
	}

	figure {
		margin: 0;
		position: relative;

	}

	
	.scroll-container {
  display: flex;
  overflow-x: auto; /* Allow horizontal scrolling */
  overflow-y: visible; /* Ensure halos aren't clipped */
  padding: 4rem; /* Adjust to provide space for halos */
  scroll-snap-type: x mandatory;
  background-color: #000000;
  position: relative; /* Needed for positioning */
}

.masonry {
  list-style: none;
  padding: 0;
  margin: 0 auto;
}

.masonry-item {
  position: relative;
  margin-top: 6rem;
  display: block;
}

.image-container {
  position: relative;
  width: 15rem;
  height: 15rem;
  border-radius: 50%;
  margin: 0 auto;
}

.image-container::before,
.image-container::after {
  content: "";
  position: absolute;
  border-radius: 50%;

}

.image-container::before {
  top: -10px;
  left: -10px;
  width: calc(100% + 20px);
  height: calc(100% + 20px);
  border: 2px solid #f374ff;
  box-shadow: 
  0 0 10px 5px rgba(243, 116, 255, 0.7)/* Full horizontal glow */
 
  
}

.image-container::after {
  top: -32px;
  left: -32px;
  width: calc(100% + 65px);
  height: calc(100% + 65px);
  border: 2px solid #84ebe8;
  box-shadow: 0 0 7px 5px #73cadb;
}

img {
  width: 100%;
  height: 100%;
  border-radius: 50%;
}

.strikje {
  position: absolute; /* Positioning relative to the .image-container */
  top: -17%; /* Adjust this value to move the strikje image above */
  left: 50%;
 z-index: 1	;
  pointer-events: none; /* Prevent the strikje image from interfering with interactions */
}

.strikje img {
  width: 100%;
  height: 100%;
  object-fit: contain;
  scale: 5;
}

.strikje::before {
  content: "";
  position: absolute;
  top: -12px;
  left: 62%;
  transform: translateX(-50%); /* Center the line horizontally */
  width: 2px; /* Width of the vertical line */
  height: 30px; /* Adjust height as needed */
  background-color:#84ebe8; 
  box-shadow: 0 0 7px 3px #73cadb;
  z-index: -1; 
}

/*  */
	figcaption {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background-color: rgba(0, 0, 0, 0.6);
		color: white;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		opacity: 0;
		transition: opacity 0.3s ease-in-out;
		border-radius: 60%;
	}

	h2 {
		font-size: 16px;
		margin: 0.5rem 0;
		text-align: center;
		-webkit-text-stroke: 0.2px #ffff00;
		border-radius: 60%;
	}

	/* Responsiee layout */
	@media (min-width: 600px) {
		.masonry {
			column-count: 2;
		}
	}

	@media (min-width: 900px) {
		.masonry {
			column-count: 3;
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