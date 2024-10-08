<!-- Filters workspace -->
<div class="filteredList">
	<button class="filter-option" data-filter="*" tabindex="0">All objects</button>
	<button class="filter-option" data-filter="Pottery" tabindex="0">Pottery</button>
	<button class="filter-option" data-filter="Islamic art" tabindex="0">Islamic art</button>
	<button class="filter-option" data-filter="Tapestry" tabindex="0">Tapestry</button>
	<button class="filter-option" data-filter="Glass" tabindex="0">Glass</button>
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

    .filter-option:focus {
  outline: 5px solid #007bff;
  
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
		}
	}
</style>
