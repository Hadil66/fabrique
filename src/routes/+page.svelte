<script>

    let showMenu = false

    function toggleMenu() {
        showMenu = !showMenu
    }
  
  </script>

<nav>
    <button id="open-menu" on:click={toggleMenu}>
        <svg xmlns="http://www.w3.org/2000/svg" width="30" height="30" viewBox="0 0 24 24" fill="none">
            <g id="Menu / Menu_Duo_MD">
            <path id="Vector" d="M5 15H19M5 9H19" stroke="#000000" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
            </g>
            </svg>
    </button>
    <div id="dropdownmenu" class:showMenu={showMenu}>
        <div id="nav-buttons">
            <button> tickets </button>
            <button><svg scale="0." xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" fill="#000000" height="30" width="30" version="1.1" id="Capa_1" viewBox="0 0 297 297" xml:space="preserve"><path d="M148.5,0C87.43,0,37.747,49.703,37.747,110.797c0,91.026,99.729,179.905,103.976,183.645  c1.936,1.705,4.356,2.559,6.777,2.559c2.421,0,4.841-0.853,6.778-2.559c4.245-3.739,103.975-92.618,103.975-183.645  C259.253,49.703,209.57,0,148.5,0z M148.5,79.693c16.964,0,30.765,13.953,30.765,31.104c0,17.151-13.801,31.104-30.765,31.104  c-16.964,0-30.765-13.953-30.765-31.104C117.735,93.646,131.536,79.693,148.5,79.693z"/></svg> venues </button>
            <button> العربية </button>
            <button  on:click={toggleMenu}> <svg fill="currentColor" height="30" viewBox="0 0 30 30" width="30" xmlns="http://www.w3.org/2000/svg"><path d="m20.7 10.8-1.5-1.5-4.2 4.3-4.2-4.3-1.5 1.5 4.3 4.2-4.3 4.2 1.5 1.5 4.2-4.3 4.2 4.3 1.5-1.5-4.3-4.2z"></path></svg> close </button>
        </div>

            <ul id="nav-1">
                <a href="#"><div class="arabic">قصصنا </div> stories </a>
                <a href="#"><div class="arabic"> الفعاليات </div> what's on</a>
                <a href="#"><div class="arabic"> زيارة </div> visit </a>
            </ul>

            <h3>Find everything for </h3>
            <ul id="nav-2">
                <li><a href="#">families and children</a></li>
                <li><a href="#">schools</a></li>
                <li><a href="#">researchers</a></li>
                <li><a href="#">shop</a></li>
                <li><a href="#">about us</a></li>
            </ul>

            <ul id="nav-3">
                <li><a href="#">careers</a></li>
                <li><a href="#">press</a></li>
                <li><a href="#">corporate</a></li>
                <li><a href="#">host your event</a></li>
                <li><a href="#">contact</a></li>
                <li><a href="#">accessibility</a></li>
                <li><a href="#">terms and conditions</a></li>
                <li><a href="#">cookie policy</a></li>
            </ul>

            <svg class="logo__svg logo__svg--en" height="150" preserveAspectRatio="xMinYMid meet" viewBox="0 0 627 150" width="627" x="0" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" y="0"><use fill="currentColor" x="0" xlink:href="#logo-en" y="0"></use></svg>
        </div>
</nav>

<style>
    /* alegemene styling */
    ul {
        list-style-type: none;
    }

    a {
        text-decoration: none;
        color: black;
    }

    h3 {
        margin: 0 0 0 0.5em;
    }
    /* einde algemene styling */

    /*  font styling nog aanpassen  */

    #dropdownmenu { 
        background-color: #FFE40C;
        margin: 0;
        overflow: hidden scroll;
        height: 100vh;
        width: 100vw;
        display: none;
    }

    .showMenu {
        display: block;    
    }

    #nav-buttons {
        display: flex;
        flex-direction: row;
        margin: 0.5em;
    }

    #nav-buttons button, #open-menu {
        display: flex;
        align-items: center;
        background: none;
        border: none;
        font-weight: 600;     
        font-size: 1em;
        padding: 0.5em;
        cursor: pointer;
        text-transform: uppercase;
    }

    #nav-buttons button:nth-of-type(1) {
        background-color: #F9FF1E;
        border: black solid 1px;
    }

    #nav-buttons button:nth-of-type(2) svg {
        scale: 0.7;
    }

    #nav-1, #nav-2, #nav-3 {
        font-size: 2.2em;
        display: flex;
        flex-direction: column;
        gap: 0.5em;
        padding: 0.5em;
        border-bottom: black solid 1px;
    }
    
    #nav-1 a {        
        font-weight: bold;
        display: flex;
        flex-direction: column;
        text-transform: uppercase;
    }

    #nav-2 {
        font-size: 2em;
        gap: 0;
        margin: 0;
    }

    #nav-2 li, #nav-3 li {
        text-transform: capitalize;
    }

    #nav-2 li:nth-of-type(4), #nav-3 li:nth-of-type(6) {
        margin-top: 2em;
    }

    #nav-3 {
        font-size: 1.3em;
        border-bottom: none;
    }



</style>