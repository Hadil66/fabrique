
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
    <span class="menu-icon">
        <span></span>
        <span></span>

    </span>
    <button class="menu-button">MENU</button>
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
       nav ul {
           list-style: none;
           display: none;
       }
   
       nav ul li {
           white-space: nowrap; /* Prevent line breaks */
       }
   
       nav ul li:hover {
           text-decoration: underline;
           cursor: pointer;
       }
   
       .ticket-nav-item {
           background-color: yellow;
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
   
       /* MENU BUTTON  */
       .menu-button {
           background-color:transparent;
           border: none;
           font-family: 'DIN Next', sans-serif;
           font-style: normal;
           font-weight: 600;
           font-size: 16px;
           margin-bottom: 0;
       }
   
       .menu-icon {
           display: block;
           width: 26px;
           height: 8px;
           position: relative;
           cursor: pointer;
       }
   
       .menu-icon span {
           display: block;
           width: 100%;
           height: 2.2px;
           background-color: #000;
           margin-bottom: 4px;
       }
   
   /*  MEDIA QUERY */
   
       /* Hide Tickets on screens smaller than 360px */
       @media (max-width: 359px) {
           .ticket-nav-item {
               display: none;
           }
       }
   
       @media (max-width: 900px) {
           ul li:not(.ticket-nav-item) {
           display: none; /* Hide all except the ticket-nav-item */
       }
   
       .ticket-nav-item {
           display: block; /* Make sure the ticket-nav-item is always visible */
       }
       /* nav {
               min-width: 20rem;
           } */
       }
      
   
       /* Desktop */
       @media (min-width: 1020px) {
       
           nav ul { 
             
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
   </style>