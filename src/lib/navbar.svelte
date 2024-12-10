<script>
    import Dropdown from '$lib/Dropdown.svelte'

	let showMenu = false;
	function toggleMenu() {
        showMenu = !showMenu;
      }

</script>

<nav>
    <a href="#">
        <div class="logo-container">
            <img class="logo-qatar" src="/logo-qatar.png" alt="Qatar Museums">
            <p class="title">  <span>متاحف قطر</span> Qatar Museums</p>  
        </div>  
    </a>
</nav>


<style>

   /* NAV BAR */
nav {
    display: flex;
    align-items: center; /* Center the items vertically */
    justify-content: space-between;
    font-family: 'DIN Next', sans-serif;
    font-style: normal;
    font-weight: 600;
    font-size: 16px;
    line-height: 20px;
    border-bottom: 1px solid #000;
    width: 100%;
    height: 3.7em;
    position: fixed;
    z-index: 33;
    background: white;
    top: 0;
}


.title {
    margin-left: 0.5rem;    
    white-space: nowrap;  
}
/* LOGO */

.logo-qatar {
    object-fit: cover;
    width:7rem ;
    scale: 0.8;
    background-color: transparent;
}

.logo-container {
    display: flex;
    align-items: center;
    width: 	100%;
}


</style>