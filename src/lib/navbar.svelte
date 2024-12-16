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
    <ul>
        <li>
            <span>قصص</span>
            <a href="#"> STORIES</a>
        </li>
        <li>
            <span>ما هو الجديد</span> 
            <a href="#"> WHAT'S ON</a>
        </li>
        <li>
            <span>المجموعة</span> 
            <a href="#"> COLLECTION</a>
        </li>
        <li>
            <span>زيارة</span> 
            <a href="#">VISIT</a>
        </li>
        <li>
            <a  class="ticket-nav-item" href="#"> TICKETS</a>
           </li>
        <li>
            <a href="#"> MEMBERS</a>
           
        </li>
        <li>
            <a href="#">VENUES</a>
            
        </li>
        <li>
            <a href="/menu">
                <svg
xmlns="http://www.w3.org/2000/svg"
width="30"
height="30"
viewBox="0 0 24 24"
fill="none"
>
<g id="Menu / Menu_Duo_MD">
  <path
    id="Vector"
    d="M5 15H19M5 9H19"
    stroke="#000000"
    stroke-width="2"
    stroke-linecap="round"
    stroke-linejoin="round"
  />
</g>
</svg>
                menu</a>
        </li>
        
    </ul>
      
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
    height: 4rem;
    position: fixed;
    z-index: 33;
    background: linear-gradient(
  to bottom,
  color(display-p3 0.913725 0.741176 0.447059 / 1),
  color(display-p3 0.913725 0.741176 0.447059 / 1) 50%,
  color(display-p3 0.913725 0.870588 0.752941 / 1) 50%,
  color(display-p3 0.913725 0.870588 0.752941 / 1)
);
/* The rectangle in which to repeat. 
   It can be fully wide in this case */
background-size: 100% 20px;
    top: 0;
}

a {
    color:#000;
    text-decoration: none;
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

/* Ul */
nav ul {
    list-style: none;
    display: flex; 
    gap: 20px;
    margin-right: 1rem;
    justify-content: flex-end;
    width: 100%;
}

nav ul li {
    white-space: nowrap; 
    display: block; 
}

nav ul li:hover {
    text-decoration: underline;
    cursor: pointer;
}

.ticket-nav-item {
    background-color: yellow;
    padding: 0.4rem;
    font-size: 16px;
    border: #000 solid 1px;
}

.ticket-nav-item:hover {
    color: #fff;
    background-color: black;
    cursor: pointer;
}

span {
    display: block;
    text-align: center;
    font-size: 20px;
}


/* MEDIA QUERY */

@media (max-width: 450px) {

.ticket-nav-item {
        display: none; 
    }
}

@media (max-width: 990px) {
    nav ul {
        display: flex; 
    }

    /* Hide all li items except .ticket-nav-item */
    nav ul li:not(.ticket-nav-item) {
        display: none;
    }
}

@media (min-width: 1020px) {
    nav ul {
        display: flex;
        align-items: center;
        gap: 20px;
        justify-content: flex-end;
        width: 100%;
    }

    nav ul li {
        display: block; /* Ensure all li items are visible on desktop */
    }
}
</style>