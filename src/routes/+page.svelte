<!-- Filters workspace -->
<div class="filteredList">
	<button class="filter-option" data-filter="*" tabindex="-1">All objects</button>
	<button class="filter-option" data-filter="Pottery" tabindex="-1">Pottery</button>
	<button class="filter-option" data-filter="Islamic art" tabindex="-1">Islamic art</button>
	<button class="filter-option" data-filter="Tapestry" tabindex="-1">Tapestry</button>
	<button class="filter-option" data-filter="Glass" tabindex="-1">Glass</button>
</div>

<style>
	* {
		transition: 0.2s;
		font-family: 'DIN Next', sans-serif;
	}

	.filter-option {
		background-color: #464646;
		color: white;
		border: none;
		height: 50px;
		width: 100px;
		font-size: 19px;
		margin-right: 0.5em;
	}

	.filteredList {
		position: absolute;
		bottom: 5em;
		overflow: scroll;
		display: flex;
	}

	@media only screen and (min-width: 600px) {
		.filteredList {
			position: absolute;
			bottom: 6.7em;
			overflow: hidden;
			display: flex;
			left: 2em;
			justify-content: center;
		}
	}
</style>
