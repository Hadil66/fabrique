<script>
	import { activeFilter } from "$lib/store";
	import Header from '$lib/molecules/Header.svelte';
  	import ArtObject from '$lib/molecules/ArtObject.svelte';
  	import Lenis from '@studio-freight/lenis';
  	import { onMount, onDestroy } from 'svelte';
	import Searchbar from '$lib/molecules/searchbar.svelte';
	import Filters from "$lib/molecules/Filters.svelte";

	export let data;
  
	let lenis;
	let scrollContainer; 

	function handleScroll() {
  		if (pastHalfScrollWidth()) { 
			backToHalfScrollWidth()
  		}
	}
	
	function pastHalfScrollWidth() {
		return scrollContainer.scrollLeft >= scrollContainer.scrollWidth / 2
	}
	
	function backToHalfScrollWidth(){
		scrollContainer.scrollLeft -= scrollContainer.scrollWidth / 2;
	}

	onMount(() => {
	// Initialize Lenis
	lenis = new Lenis({ infinite: true, syncTouch: true });

	// Define the requestAnimationFrame function
	function onRaf(time) {
	lenis.raf(time);
	requestAnimationFrame(onRaf);
	}

	// Start the animation frame loop
	requestAnimationFrame(onRaf);
	});

	onDestroy(() => {
		// Cleanup if necessary (e.g., stop the animation frame)
		lenis = null; // or any other cleanup logic if required
	});console.log('Scroll container:', scrollContainer);
	// console.log('Active filter:', $activeFilter);
	// console.log('Techniques:', techniques);
	console.log('Lenis:', lenis);
	
	const techniques = ["Pottery", "Islamic art", "Tapestry", "Glass"];

</script>

<Header />

<div class="scroll-container"
bind:this={scrollContainer}
  on:scroll={handleScroll}>
  <div class="column-reverse">
		<ul class="masonry">
			{#each data.artObjects as art, index}
			<ArtObject art={art} techniques={techniques} index={index}/>
			{/each}
		</ul>
	</div>

	<div class="column">
		<ul class="masonry">
			{#each data.artObjects as art, index}
			<ArtObject art={art} techniques={techniques} index={index}/>
			{/each}
		</ul>
	</div>

	<div class="column-reverse">
		<ul class="masonry">
			{#each data.artObjects as art, index}
			<ArtObject art={art} techniques={techniques} index={index}/>
			{/each}
		</ul>
	</div>

	<div class="column">
		<ul class="masonry">
			{#each data.artObjects as art, index}
			<ArtObject art={art} techniques={techniques} index={index}/>
			{/each}
		</ul>
	</div>
</div>

<div>
	<Searchbar/>
	<Filters />
</div>

<style>
	.scroll-container {
		display: grid;
		overflow-x: auto;
		padding: 1rem;
		margin: 2.5rem;
		scroll-snap-type: x mandatory;
		grid-template-columns: repeat(4, 1fr);
		overflow-y: hidden;
	}

	.column {
		display: flex;
		flex-direction: column;
		margin: 0 1em;
	}

	.column-reverse {
		animation: adjust-position linear forwards;
		animation-timeline: scroll(root block);
		transform: translateY(calc(-100% + 100vh));
		flex-direction: column-reverse;
	}

	@keyframes adjust-position {
		from {
			transform: translateY(calc(-100% + 100vh));
		}

		to {
			transform: translateY(calc(100% - 100vh));
		}
	}

	.masonry {
		column-count: 1;
		column-gap: 1rem;
		list-style: none;
		padding: 0;
	} 
</style>