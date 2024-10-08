<script>
	export let data;
	console.log(data); // Hiermee kun je zien hoe de API-respons eruitziet
	import Search from '$lib/Search.svelte'; // Icoon wordt gebruikt voor de searchbar
	let filterText = '';
	import Navbar from '$lib/navbar.svelte';
</script>

<Navbar />

<ul class="masonry">
	{#each data.artObjects.filter((art) => art.title
			.toLowerCase()
			.includes(filterText.toLowerCase())) as art}
		<li class="masonry-item">
			<figure>
				<img src={'https://fdnd-agency.directus.app/assets/' + art.image} alt={art.title} />
				<figcaption>
					<h2>{art.title}</h2>
					<a href="#" class="button">Meer info</a>
				</figcaption>
			</figure>
		</li>
	{/each}
</ul>

<!-- Filters/search workspace Ellenoor-->
<div class="filteredList">
	<button class="filter-option" data-filter="*" tabindex="0">All objects</button>
	<button class="filter-option" data-filter="Pottery" tabindex="0">Pottery</button>
	<button class="filter-option" data-filter="Islamic art" tabindex="0">Islamic art</button>
	<button class="filter-option" data-filter="Tapestry" tabindex="0">Tapestry</button>
	<button class="filter-option" data-filter="Glass" tabindex="0">Glass</button>
</div>

<div class="wrap">
	<div class="search">
		<input
			type="text"
			class="searchTerm"
			bind:value={filterText}
			placeholder="Search the collection"
		/>
		<button type="submit" class="searchButton" aria-label="Submit search">
			<Search />
		</button>
	</div>
</div>

<!-- Filters/search workspace Ellenoor-->

<style>
	* {
		transition: 0.2s;
		font-family: 'DIN Next', sans-serif;
	}

	.masonry {
		column-count: 1;
		column-gap: 1rem;
		list-style: none;
		padding: 0;
	}

	.masonry-item {
		break-inside: avoid;
		margin-bottom: 1rem;
		position: relative;
		overflow: hidden;
		background-color: #fff;
		border-radius: 8px;
		box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
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
	}

	/* overlay */

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

	.masonry-item:hover img {
		transform: scale(1.1);
	}
	.masonry-item:hover figcaption {
		opacity: 1;
	}

	h2 {
		font-size: 16px;
		margin: 0.5rem 0;
	}

	a {
		color: black;
		background-color: #efc715;
		padding: 0.5rem 1rem;
		border-radius: 4px;
		text-decoration: none;
		&:hover {
			background-color: #00b0f0;
		}
	}

	/* Grotere schermen: 2 kolommen voor medium en 3 voor grote schermen */
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

	/* ---- */
	/* Styling Ellenoor */
	/* ---- */
	/* Styling voor filter buttons */
	.filter-option {
		background-color: #464646;
		color: white;
		border: none;
		height: 50px;
		width: 100px;
		font-size: 19px;
		margin-right: 0.5em;
	}

	/* Styling voor tab functie */
	.filter-option:focus {
		outline: 2px solid #007bff;
		box-shadow: 0 0 0 2px #007bff;
		background-color: #007bff;
		color: #ffffff;
	}

	.filteredList {
		position: fixed;
		bottom: 5em;
		overflow: scroll;
		display: flex;
        margin-left: 1em;
	}

	/* Styling voor de zoekbalk */
	.search {
		width: 100vw;
		position: relative;
		display: flex;
	}

	.searchTerm {
		width: 100%;
		border: 2px solid black;
		border-right: none;
		padding: 0.5em 0 0 0.5em;
		color: #707070;
		font-size: 25px;
		text-decoration: underline black;
	}

	.searchTerm:focus {
		color: black;
	}

	.searchButton {
		width: 4em;
		height: 5.3em;
		padding: 0.5em;
		border-left: none;
		background: white;
		text-align: center;
		justify-content: center;
		color: black;
		cursor: pointer;
	}

	.wrap {
		position: fixed;
		bottom: 0;
	}

	@media only screen and (min-width: 600px) {
		/* Code voor filter buttons */
		.filteredList {
			position: fixed;
			left: 50%;
			transform: translateX(-50%);
			bottom: 6.7em;
		}

		/* Code voor zoekbalk  */
		.wrap {
			position: absolute;
			bottom: 6em;
			left: 2em;
			right: 2em;
		}

		.search {
			width: 60vw;
			position: fixed;
			display: flex;
            left: 50%;
			transform: translateX(-50%);
		}
	}
	/* ---- */
	/* Styling Ellenoor */
	/* ---- */
</style>
