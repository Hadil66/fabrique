<nav>
    <div class="logo-container">
        <img class="logo-qatar" src="/logo-qatar.png" alt="Qatar Museums">
        <p class="title">Qatar Museums</p>
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
        <button class="menu-button">MENU</button>
    </ul>
    <div>
        </div>
</nav>

<style>
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
    }

    .title {
        margin-left: 0.5rem;
    }
    
    .logo-qatar {
        object-fit: cover;
        width: 5rem;
        height: 5rem;
    }
 
    .logo-container {
        display: flex;
        align-items: center;
    }

    ul {
        list-style: none;
        display: flex;
        align-items: center;
        gap: 20px;
        margin-right: 50px; /* Adjust margin-right to move the ul to the right */
        justify-content: flex-end;
    }
    ul li:hover {
        text-decoration: underline;
        cursor: pointer;
    }

    .ticket-nav-item {
        background-color: yellow;
        padding: 1rem;
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

    .menu-button {
        background-color:transparent;
        border: none;
        font-family: 'DIN Next', sans-serif;
        font-style: normal;
        font-weight: 600;
        font-size: 16px;
    }

</style>