<script>
    	import Search from '$lib/Search.svelte'; // Icoon wordt gebruikt voor de searchbar
        let filterText = '';
</script>

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

<style>
.search {
    width: 100vw;
    position: relative;
    display: flex;
    align-items: center; 
    border: 2px solid var(--black); 
    border-radius: 4px; 
    overflow: hidden;
    background: var(--argentinian-blue);
}

.search::after {
    content: '';
    position: absolute;	
    bottom: 0.5em;
    left: 0.5rem;
    width: 93%;
    height: 1px; 
    background-color: var(--black);
}

.searchTerm {
    flex: 1; 
    border: none; 
    padding: 0.5em 0.5em;
    font-size: 24px;
    background: transparent;
}

/* text styling */
.searchTerm::placeholder {
    color: var(--black);
    text-transform: uppercase;
    letter-spacing: 0.1rem;
}

.searchButton {
    width: 4em;
    height: 100%; 
    border: none; 
    background: transparent; /* Same background as the search bar */
    display: flex;
    align-items: center;
    justify-content: center;
    padding: 0;
    margin-left: 0.3rem;

    cursor: pointer;
}

.searchButton i {
    display: block;
    width: 20px;
    height: 20px;
    background: url('path-to-your-search-icon.svg') no-repeat center;

}
.searchButton:hover {
    transform: scale(1.2);
}

.wrap {
    position: fixed;
    bottom: 0;
    width: 100%;
}

@keyframes loadingAnimation {
0% {
    width: 0;
}
50% {
    width: 100%; /* Expand to full width */
}
100% {
    width: 0; /* Shrink back to 0 */
}
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

</style>