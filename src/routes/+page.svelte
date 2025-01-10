<script>
	export let data;
	console.log(data); // Bekijk de API-respons in de console
  
	import Header from '$lib/molecules/Header.svelte';
	import Searchbar from '$lib/molecules/searchbar.svelte';
	import { activeFilter } from "$lib/store";
	import Filters from "$lib/molecules/Filters.svelte";
  
	let scrollContainer;
  
	// Functie om het scrollgedrag te beheren
	function handleScroll() {
	  // Controleer of de gebruiker halverwege de scrollcontainer is gescrolld
	  if (scrollContainer.scrollLeft >= scrollContainer.scrollWidth / 2) {
		// Scroll terug naar het begin van de tweede helft van de inhoud
		scrollContainer.scrollLeft -= scrollContainer.scrollWidth / 2;
	  }
	}
  
	const techniques = ["Pottery", "Islamic art", "Tapestry", "Glass"];
  </script>
  
  <Header />
  
  <div class="scroll-container" bind:this={scrollContainer} on:scroll={handleScroll}>
	<ul class="masonry">
	  {#each data.artObjects as art, index}
		<!-- Dupliceren van inhoud voor infinite scroll effect -->
		<li
		  class="masonry-item"
		  class:hidden={$activeFilter !== "*" && $activeFilter !== techniques[index % techniques.length]}
		  data-category={techniques[index % techniques.length]}
		>
		  <figure>
			<picture>
			  <source srcset={"https://fdnd-agency.directus.app/assets/" + art.image + ".avif"} type="image/avif" />
			  <source srcset={"https://fdnd-agency.directus.app/assets/" + art.image + ".webp"} type="image/webp" />
			  <img
				src={"https://fdnd-agency.directus.app/assets/" + art.image}
				alt={art.title}
				height={art.height}
				width={art.width}
				loading="lazy"
			  />
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
	<Searchbar />
	<Filters />
  </div>
  
  <style>
	.scroll-container {
	  overflow-y: auto;
	  overflow-x: auto;
	  padding: 1rem;
	  margin: 2.5rem;
	  scroll-snap-type: both mandatory;
	  width: 100%;
	  white-space: nowrap;
	}
  
	.scroll-container::-webkit-scrollbar {
	  width: 0px; /* Verberg scrollbar */
	}
  
	.masonry {
	  display: grid;
	  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
	  grid-auto-rows: 200px;
	  gap: 1rem;
	  width: max-content;
	}
  
	.masonry-item {
	  background-color: #fff;
	  border-radius: 8px;
	  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
	  overflow: hidden;
	  position: relative;
	  transition: opacity 0.3s, transform 0.3s ease-in-out;
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
	  transform: scale(1.1);
	}
  
	figure {
	  margin: 0;
	  position: relative;
	}
  
	img {
	  width: 100%;
	  height: 100%;
	  object-fit: cover;
	  display: block;
	  border-radius: 8px;
	}
  
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
	}
  
	.masonry-item:hover figcaption,
	.masonry-item:focus figcaption {
	  opacity: 1;
	}
  
	h2 {
	  font-size: 16px;
	  margin: 0.5rem 0;
	  text-align: center;
	  -webkit-text-stroke: 0.2px #ffff00;
	}
  
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
  
	@media (prefers-reduced-motion) {
	  .masonry-item {
		transition: none;
	  }
  
	  img {
		transition: none;
	  }
	}
  </style>
  