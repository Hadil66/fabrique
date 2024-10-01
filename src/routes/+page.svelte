<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<!-- Filters workspace -->
<!-- Control buttons -->
<div class="filteredList">
    <h3>Filters</h3>
    <button class="filter-option" data-filter="walks" tabindex="-1">Walks</button> 
    <button class="filter-option" data-filter="swims" tabindex="-1">Swims</button> 
    <button class="filter-option" data-filter="flies" tabindex="-1">Flies</button> 
    <button class="filter-option" data-filter="*" tabindex="-1">All</button>

    <h3>Animals</h3>
    <div class="dog walks">Dog</div>
    <div class="eagle flies">Eagle</div>
    <div class="cow walks">Cow</div>
    <div class="shark swims">Shark</div>
    <div class="canary flies">Canary</div>
    <div class="human walks">Human</div>
    <div class="salamander swims walks">Salamander</div>
  </div>

  <div class="wrap">
    <div class="search">
       <input type="text" class="searchTerm" placeholder="What are you looking for?">
       <button type="submit" class="searchButton">
         <i class="fa fa-search"></i>
      </button>
    </div>
 </div>

<style>
button[data-filter="walks"]:focus ~ div:not([class*="walks"]) {
  display:none;
}

button[data-filter="swims"]:focus ~ div:not([class*="swims"]) {
  display:none;
}

button[data-filter="flies"]:focus ~ div:not([class*="flies"]) {
  display:none;
}

</style>