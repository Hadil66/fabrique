<script>
	export let data;

	import Header from '$lib/molecules/Header.svelte';
	import Search from '$lib/Search.svelte'; // Icoon wordt gebruikt voor de searchbar
	import Searchbar from '$lib/molecules/searchbar.svelte';
	import { activeFilter } from "$lib/store";
	import Filters from "$lib/molecules/Filters.svelte";
	import { onMount } from 'svelte';
	import Cursor from '$lib/Atoms/Icons/Cursor.svelte';

    onMount( async () => { 
		window.addEventListener('scroll', () => {
		const playAudio = document.querySelector("audio");

		if (window.scrollY > 10) {
			playAudio.play();
		}
		});
	});
	
	let filterText = '';
	let scrollContainer; // variable scroll container. 

function handleScroll() {
  // Als de gebruiker halverwege de scrollcontainer is gescrolld...
  if (scrollContainer.scrollLeft >= scrollContainer.scrollWidth / 2) { 
    // ... scroll dan terug naar het begin van de tweede helft van de inhoud.
    scrollContainer.scrollLeft -= scrollContainer.scrollWidth / 2;
  }
}
  
  
	const techniques = ["Pottery", "Islamic art", "Tapestry", "Glass"];
	</script>


<Header />
<audio autoplay loop src="/AHS.mp3"></audio>
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
				<img src="/bloody-hands.png">
			</figcaption>
		</figure>
	  </li>
	{/each}
  </ul>
  <img class="twisty" src="/twisty.png">

  <img class="twisty" src="/twisty.png">

</div>

<div>
	<Searchbar/>
   <Filters />
</div>

<style>
	.scroll-container {
		display: flex;
		overflow-x: auto;
		padding: 0;
		margin: 0;
		scroll-snap-type: x mandatory;
	}

	.masonry {
		column-count: 1;
		column-gap: 1em;
		list-style: none;
		padding: 0 6em;
		margin: 0;
	}

	.masonry-item {
		break-inside: avoid;
		display: block;
		background-color: #fff;
		border-radius: 8px;
		box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
		margin-bottom: 1rem;
		position: relative;
		overflow: hidden;
		transition: opacity 0.3s;
		z-index: 24;
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

	.masonry-item:hover figcaption,
	.masonry-item:focus figcaption {
		opacity: 0.5;
	}

	
	figcaption img {
		scale: 0.7;
	}

	figure {
		margin: 0;
		position: relative;
	}

	img {
		width: 100%;
		height: auto;
		display: block;
		border-radius: 8px;
		transition: transform 0.3s ease-in-out;
		filter: grayscale(0.5);
	}

	figcaption {
		position: absolute;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background-color: white;
		color: white;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		opacity: 0;
		transition: opacity 0.3s ease-in-out;
	}

	h2 {
		font-size: 16px;
		margin: 0.5rem 0;
		text-align: center;
		-webkit-text-stroke: 0.2px lch(37 90.45 43.27);
	}

	.twisty {
		position: fixed;
		opacity: 0.5;
		width: 300px;
	}

	.twisty:nth-of-type(1) {
		animation: jumpscare1 0.5s forwards;
		animation-range: 0vh 100vh;
		animation-timeline: scroll();
		left: -5em;
		top: 8em;
	}

	.twisty:nth-of-type(2) {
		animation: jumpscare2 0.5s forwards;
		animation-timeline: scroll();
		top: 15em;
		right: -6em;
	}

	@keyframes jumpscare1 {
		0% { transform: translateX(-10vw); }
		100% { transform: translateX(0); }
	}

	@keyframes jumpscare2 {
		0% { transform: translateX(10vw); }
		100% { transform: translateX(0); }
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