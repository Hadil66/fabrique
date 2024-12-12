<script>
  import { activeFilter } from "$lib/store";

  function setFilter(filter) {
    activeFilter.set(filter);
  }
</script>

<ul>
  <li>
    <button
      on:mouseover={() => activeFilter.set("*")}
      on:mouseleave={() => ($activeFilter = "*")}>All objects</button
    >
  </li>
  <li>
    <button
      on:mouseover={() => activeFilter.set("Pottery")}
      on:mouseleave={() => ($activeFilter = "*")}>Pottery</button
    >
  </li>
  <li>
    <button
      on:mouseover={() => activeFilter.set("Islamic art")}
      on:mouseleave={() => ($activeFilter = "*")}>Islamic art</button
    >
  </li>
  <li>
    <button
      on:mouseover={() => activeFilter.set("Tapestry")}
      on:mouseleave={() => ($activeFilter = "*")}>Tapestry</button
    >
  </li>
  <li>
    <button
      on:mouseover={() => activeFilter.set("Glass")}
      on:mouseleave={() => ($activeFilter = "*")}>Glass</button
    >
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
      color: var(--black);
    }
  }

  ul button {
    background-color: #464646;
    border: none;
    border-radius: 4px;
    color: var(--white);
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

/* DIT GAA NIET SAMEN MET DE HOVER STYLING */
/*   
  ul li:nth-of-type(1) button {
    box-shadow: 2px 2px 2px var(--rose);
  }

  ul li:nth-of-type(2) button {
    box-shadow: 2px 2px 2px var(--rose-pink);
  }

  ul li:nth-of-type(3) button {
    box-shadow: 2px 2px 2px var(--gold);
  }

  ul li:nth-of-type(4) button {
    box-shadow: 2px 2px 2px var(--persian-blue);
  }

  ul li:nth-of-type(5) button {
    box-shadow: 2px 2px 2px var(--argentinian-blue);
  } */

  @media (prefers-reduced-motion: no-preference) {
    ul li:nth-of-type(1) button:focus,
    ul li:nth-of-type(1) button:hover {
      box-shadow: inset 9em 0 0 0 var(--rose);
    }  
    
    ul li:nth-of-type(2) button:focus,
    ul li:nth-of-type(2) button:hover {
      box-shadow: inset 8.5em 0 0 0 var(--rose-pink);
    }  
    
    ul li:nth-of-type(3) button:focus,
    ul li:nth-of-type(3) button:hover {
      box-shadow: inset 8.5em 0 0 0 var(--gold);
    }  
    
    ul li:nth-of-type(4) button:focus,
    ul li:nth-of-type(4) button:hover {
      box-shadow: inset 8.5em 0 0 0 var(--persian-blue);
      color: var(--white);
    }
    ul li:nth-of-type(5) button:focus,
    ul li:nth-of-type(5) button:hover {
      box-shadow: inset 8.5em 0 0 0 var(--argentinian-blue);
    }
  }

  ul button:hover,
  ul button:focus {
    color: var(--black);
  }

  @media (min-width: 600px) {
    ul {
      width: max-content;
    }
  }
</style>