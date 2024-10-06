<script>
    import Dropdown from '$lib/Dropdown.svelte'

	let showMenu = false;
	function toggleMenu() {
        showMenu = !showMenu;
      }

</script>
<nav>
    <div class="logo-container">
        <img class="logo-qatar" src="/logo-qatar.png" alt="Qatar Museums">
        <p class="title">  <span>متاحف قطر</span> Qatar Museums</p>
    </div>  
    <ul>
        <li>
            <span>قصص</span> STORIES
        </li>
        <li>
            <span>ما هو الجديد</span> WHAT'S ON
        </li>
        <li>
            <span>المجموعة</span> COLLECTION
        </li>
        <li>
            <span>زيارة</span> VISIT
        </li>
        <li class="ticket-nav-item">TICKETS</li>
        <li>MEMBERS</li>
        <li>VENUES</li>
        
    </ul>
    
    <Dropdown />    
    </nav>

<style>
    nav {
        display: flex;
        align-items: center; /* Center the items vertically */
        justify-content: space-between;
        font-family: var(--default-font-family);
        font-style: normal;
        font-weight: 600;
        font-size: 16px;
        line-height: 20px;
        border-bottom: 1px solid #000;
        width: 100%;
        height: 4rem;
    }
    
    .title {
        margin-left: 0.5rem;    
        white-space: nowrap;  
    }

    /* LOGO */
    
    .logo-qatar {
        object-fit: cover;
        width:7rem ;
        height: 5rem;
        scale: 0.8;
        background-color: transparent;
    }
 
    .logo-container {
        display: flex;
        align-items: center;
        width: 	100%;
    }

    /* Ul */
     ul:nth-of-type(1) {
        list-style: none;
        display: none;
    }

     ul:nth-of-type(1) li {
        white-space: nowrap; /* Prevent line breaks */
    }

     ul:nth-of-type(1) li:hover {
        text-decoration: underline;
        cursor: pointer;
    }

    .ticket-nav-item {
        background-color: var(--nav-bg);
        padding: 0.5rem;
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

/*  MEDIA QUERY */

    /* Hide Tickets on screens smaller than 360px */
    @media (max-width: 359px) {
        .ticket-nav-item {
            display: none;
        }
    }

    /* @media (max-width: 900px) { */
        /* ul li:not(.ticket-nav-item, #nav-1, #nav-2, #nav-3) { */
         /* display: none; Hide all except the ticket-nav-item */
    /* } */

    /* .ticket-nav-item { */
        /* display: block; Make sure the ticket-nav-item is always visible */
    /* } */
    /* nav {
            min-width: 20rem;
        } */
    /* } */
   

    /* Desktop */
    @media (min-width: 1020px) {
    
         ul:nth-of-type(1) { 
          
            display: flex;
            align-items: center;
            gap: 20px;
            margin-right: 1rem;
            justify-content: flex-end;
            width: 100%;
        }
    
    }   
    .menu-button {
        display: block;
    }


    /* einde RUKIYA styling */

    /*  font styling nog aanpassen  */
    #dropdownmenu {
        display: none;
    }

    #menuIMG  {
        display: none;
    }    

    #dropdownmenu.showMenu {
        background-color: var(--nav-bg);
        bottom: 0;
        display: block;
        height: 100vh;
        left: 0;
        margin: 0;
        overflow: hidden scroll;
        position: absolute;
        right: 0;
        top: 0;
    }

    #nav-buttons {
        display: flex;
        flex-direction: row;
        margin: 0.5em;
    }

    #nav-buttons button,
    #open-menu {
        align-items: center;
        background: none;
        border: none;
        cursor: pointer;
        display: flex;
        font-size: 1em;
        font-weight: 600;
        padding: 0.5em;
        text-transform: uppercase;
    }

    #nav-buttons button:nth-of-type(1) {
        background-color: #f9ff1e;
        border: black solid 1px;
    }

    #dropdownmenu.showMenu #nav-buttons button:nth-of-type(1) {
        background-color: black;
        color: white;
    }


    #nav-buttons button:nth-of-type(2) svg {
        scale: 0.7;
    }

    #nav-buttons:nth-of-type(4) {
        position: absolute;
        left: 0.5em;
    }

    ul {
        border-bottom: black solid 1px;
        display: flex;
        flex-direction: column;
        font-size: 2.2em;
        gap: 0.5em;
        padding: 0.5em;
    }

    #nav-1 a {
        display: flex;
        flex-direction: column;
        font-weight: bold;
        text-transform: uppercase;
    }

    #nav-2 {
        font-size: 2em;
        gap: 0;
        margin: 0;
    }

    #nav-2 li,
    #nav-4 li {
        text-transform: capitalize;
    }

    #nav-2 li:nth-of-type(4),
    #nav-4 li:nth-of-type(6) {
        margin-top: 2em;
    }

    #nav-4 {
        border-bottom: none;
        font-size: 1.3em;
    }

    @media (min-width: 530px) {
        #nav-1 {
            display: flex;
            flex-direction: row;
            gap: 1em;
        }

        #nav-buttons {
            justify-content: end;
        }
    }

    @media (min-width: 800px) { 
        #dropdownmenu.showMenu {
            display: grid; 
            grid-template-columns: 0.6fr 1fr; 
            grid-template-rows: repeat(2, 1fr) 0.1fr repeat(3, 1fr);
            gap: 0px 0px; 
        }

        #menuIMG {
            display: block;
            grid-area: 1 / 1 / 7 / 2; 
            height: 100vw;
            overflow: hidden;
            width: 90%;
            object-fit: cover;
        }

        #nav-buttons {
            grid-area: 1 / 2 / 2 / 3;
            height: 3em;
        }

        #nav-1 {
             grid-area: 2 / 2 / 3 / 3; 
        }

        h3 {
            grid-area: 3 / 2 / 4 / 3;
            height: max-content;
        }

        #nav-2 {
             grid-area: 4 / 2 / 5 / 3; 
        }

        #nav-4 {
             grid-area: 5 / 2 / 6 / 3; 
        }

        svg {
            grid-area: 6 / 2 / 7 / 3;
        }


    }

    @media (min-width: 1180px) {
        #dropdownmenu.showMenu {
            display: grid;
            grid-template-columns: 0.7fr 1fr 1fr;
            grid-template-rows: 1fr 1fr 0.25fr 1fr 1fr;
            gap: 0;
        }

        #menuIMG {
            grid-area: 1 / 1 / -1 / 2;
            object-fit: fill;            
            height: 100%;
            overflow: hidden;
        }

        #nav-buttons {
            align-items: center;
            background: none;
            border: none;
            cursor: pointer;
            display: flex;
            flex-direction: row;
            font-size: 1em;
            font-weight: 600;
            grid-area: 1 / 3 / 2 / 4;
            margin: 0.5em;
            padding: 0.5em;
            text-transform: uppercase;
        }

        #nav-1 {
            grid-area: 2 / 2 / 3 / -1;
        }

        h3 {
            border-right: black solid 1px;
            grid-area: 3 / 2 / 4 / 3;
            height: max-content;
        }

        #nav-2 {
            border-bottom: none;
            border-right: black solid 1px;
            grid-area: 4 / 2 / 5 / 3; 
        }

        #nav-4 {
            grid-area: 4 / 3 / 5 / 4; 
        }

        svg {
            border-left: black solid 1px;
            grid-area: 5 / 3 / 6 / 4;
        }
    }

</style>
