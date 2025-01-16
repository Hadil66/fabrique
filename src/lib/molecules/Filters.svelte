<script>
  import { activeFilter } from "$lib/store";
  import ArtObject from './ArtObject.svelte';

  export let artObjects = []; 
  let filteredArtObjects = artObjects; 

  function filterArtObjects(technique) {
    if (technique === 'All') {
      filteredArtObjects = artObjects;
    } else {
      filteredArtObjects = artObjects.filter(art => art.technique === technique);
    }
  }

  function isHidden(art) {
    return !filteredArtObjects.includes(art);
  }

</script>

<ul>
  <li>
    <button on:click={() => filterArtObjects('All')}>All objects</button>
  </li>
  <li>
    <button on:click={() => filterArtObjects('Pottery')}>Pottery</button>
  </li>
  <li>
    <button on:click={() => filterArtObjects('Islamic art')}>Islamic art</button>
  </li>
  <li>
    <button on:click={() => filterArtObjects('Tapestry')}>Tapestry</button>
  </li>
  <li>
    <button on:click={() => filterArtObjects('Glass')}>Glass</button>
  </li>
  <li>
    <button on:click={() => filterArtObjects('Photography')}>Photography</button>
  </li>
</ul>

<style>
  ul {
    backdrop-filter: blur(4px);
    bottom: 6em;
    display: flex;
    margin: 0;
    overflow: scroll;
    padding: 0;
    position: fixed;
    left: 50%;
    transform: translateX(-50%);
    width: 25em;
    z-index: 32;
  }

  ::-webkit-scrollbar {
    display: none;
  }

  ul li {
    cursor: pointer;
    list-style-type: "";
  }

  @media (prefers-reduced-motion) {
    ul li button:focus,
    ul li button:hover {
      box-shadow: 2px 2px 2px #989802;
      background-color: #ffff00;
      color: #000;
    }
  }

  ul button {
    background-color: #464646;
    border: none;
    border-radius: 4px;
    color: white;
    cursor: pointer;
    font-size: 18px;
    margin: 0.5em;
    padding: 0.5em;
    width: 80px;
    text-align: center;
    list-style-type: "";
    transition: 0.5s;
    width: max-content;            
  }

  @media (prefers-reduced-motion: no-preference) {
    ul button:focus,
    ul button:hover {
      box-shadow: inset 6.5em 0 0 0 #ffff00;
    }
  }

  ul button:hover,
  ul button:focus {
    color: #000;
  }

  @media (min-width: 600px) {
    ul {
      width: max-content;
    }
  }
</style>