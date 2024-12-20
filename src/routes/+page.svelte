<script>
  export let data;

  let isBookOpen = false; 

  function openBook() {
    isBookOpen = true;
  }

  function closeBook() {
    isBookOpen = false;
  }
</script>

<div class="book" class:open={isBookOpen}>
  <div class="cover" class:open={isBookOpen} on:click={openBook}>
    <div class="cover-text">
      <h1>qatar museums</h1>
	  <svg viewBox="0 0 500 500">
		<path id="curve" d="M73.2,148.6c4-6.1,65.5-96.8,178.6-95.6c111.3,1.2,170.8,90.3,175.1,97" fill="none" />
		<text width="500">
		  <textPath xlink:href="#curve">
			A Christmas Carol
		  </textPath>
		</text>
	  </svg>    
	</div>
  <div class="back-cover" on:click={closeBook}></div>
</div>
  <div class="page">
    <div class="page-content">
      <ul class="masonry">
        {#each data.artObjects as art, index}
          <li>
              <img
                src={"https://fdnd-agency.directus.app/assets/" + art.image}
                alt={art.title}
                height={art.height}
                width={art.width}
                loading="lazy"
              />
              <!-- <figcaption>
                <p>{art.title}</p>
              </figcaption> -->
          </li>
        {/each}
      </ul>
    </div>
  </div>
  <div class="side"></div>
  <div class="bottom"></div>
  <div class="shadow"></div>
</div>

<div class="background">
	<!-- STARS -->
	<div class="stars" class:open={isBookOpen}>
		<li class="small"></li>
		<li class="small"></li>
		<li></li>
		<li class="small"></li>
		<li class="small"></li>
		<li></li>
		<li></li>
		<li></li>
		<li class="small"></li>
		<li></li>
		<li></li>
		<li class="small"></li>
		<li class="small"></li>
		<li class="small"></li>
		<li class="small"></li>
		<li></li>
		<li class="small"></li>
		<li class="small"></li>
		<li class="small"></li>
		<li></li>
		<li class="small"></li>
		<li class="small"></li>
		<li></li>
		<li class="small"></li>
		<li class="small"></li>
		<li class="small"></li>
		<li class="small"></li>
		<li></li>
		<li></li>
		<li></li>
		<li></li>
		<li class="small"></li>
		<li></li>
		<li class="small"></li>
		<li class="small"></li>
		<li></li>
		<li></li>
		<li class="small"></li>
		<li></li>
		<li class="small"></li>
		<li class="small"></li>
		<li></li>
		<li class="small"></li>
		<li class="small"></li>
		<li class="small"></li>
		<li class="small"></li>
		<li></li>
		<li></li>    
	  </div>
	</div>


<style>
  .book {
    transform-style: preserve-3d;
    transform: rotateX(45deg) rotateY(0deg) rotateZ(-45deg);
    transition: transform 1s;
    position: relative;
    width: max-content;
    height: 40em;
	  margin: 5em;
    z-index: 663;
  }

  .book .side {
    width: 3em;
    height: 40em;
    background-image: url(/cover.png);
    position: absolute;
    left: -3em;
    top: 0;
    transform-origin: 100% 100%;
    transform: rotateY(-90deg) rotateX(0deg);
  }

  .book .bottom {
    width: 25em;
    height: 3em;
    background: var(--eggshell);
    position: absolute;
    bottom: 0;
    left: 0;
    transform-origin: 100% 100%;
    transform: rotateX(90deg);
  }

  .book .shadow {
    background: transparent;
    transform: translateZ(-3em);
    box-shadow: -1em 1em 0px 0px var(--eerie-black);
    z-index: 1;
    width: 25em;
    height: 40em;
    position: absolute;
    top: 0;
    left: 0;
  }

  .book .cover {
    background-image: url(/cover.png);
    background-repeat: no-repeat;
    background-position: center;
    background-size: cover;
    height: 40em;
    left: 0;
    position: absolute;
    top: 0;
    transition:
    transform 1s,
	  box-shadow 0.5s 0.2s;
    transform-origin: 0 50%;
    transform-style: preserve-3d;
    width: 25em;
    z-index: 8;
  }

  .book .cover.open {
    box-shadow: 2.2em 1em 0px 0px var(--eerie-black);
    transform: rotateX(0deg) rotateY(-180deg) rotateZ(0deg);
  }

  .book .cover-text {
  position: relative;
  z-index: 2;
}

h1, svg {
  position: absolute;
  text-transform: capitalize;
}

h1 {
  font-size: 1.5em;
  top: 10.8em;
  left: 6em;
  color: var(--eggshell);
  letter-spacing: 1px;
  width: max-content;
  width: 5.7em;
  text-align: center;
}

svg  {
  z-index: 15;
  top: 1.8em;
  left: -9em;
  width: 45em;
  height: 66vh;
  rotate: 26deg;
}

svg textPath {
	  fill: var(--eggshell);
	  font-size: 2em;
}

  .book .back-cover {
    background: var(--burgundy);
    width: 100%;
    height: 100%;
    position: absolute;
    z-index: 1;
    transform: translateZ(-0.4px);
  }

  .book .page {
    width: 25em;
    height: 40em;
    position: absolute;
    top: 0;
    left: 0;
    transform-origin: 0 50%;
    transform-style: preserve-3d;
    transition:
    transform 1s,
    box-shadow 0.5s 0.2s;
    z-index: 7;
  }

  .book .page-content {
    background-image: url(/background1.jpg);
    width: 100%;
    height: 100%;
    overflow: hidden;
    position: absolute;
  }

  .book.open {
    transform: rotateX(35deg) rotateY(0deg) rotateZ(-35deg);
  }

  /* INHOUD */

  ul {
    margin: 0.5em;
    padding: 0;
    display: flex;
    flex-direction: row;
    flex-wrap: wrap;
    padding: 0em;
    width: 24em;
    height: 39em;
    background: color(display-p3 0.125490 0.121569 0.121569 / .600000);
    border-radius: 8px;
  }
  li {
    height: 9em;
    list-style-type: "";
    width: 7em;
    margin: 0.5em;
  }

  li img {
    height: auto;
    margin: 0;
    width: 100%;
    border-radius: 8px;

  }

  li p {
    font-weight: 300;
  }

  .background {
  width:100%;
  height:100%;
  position:absolute;
  z-index:1;
}

li {
	list-style-type: "";
}
	  /*-- stars --*/
.stars{
  width:100%;
  height:100%;
  position:relative;  
  background:transparent;
  background-size:100%;
  background-position:0px 15px ;
}
.stars li {
background: radial-gradient(ellipse at center, var(--eggshell) 0%,rgba(21,118,151,0) 100%);
list-style-type: none;
width: 10px;
height: 10px;
-webkit-transform: rotate(45deg);
display: none;
position: absolute;
transition: 0.3s;
}

.stars li.open {
  display: block;
}

.stars li.small {width: 5px;height: 5px;}
.stars li:nth-child(1) {top: 46%;left: 5%;}
.stars li:nth-child(2) {top: 51%;left: 9%;}
.stars li:nth-child(3) {top: 68%;left: 10%;}
.stars li:nth-child(4) {left: 17.4%;bottom: 31%;}
.stars li:nth-child(5) {left: 18.3%;top: 68%;}
.stars li:nth-child(6) {left: 21%;bottom: 38%;}
.stars li:nth-child(7) {left: 23%;top: 62%;}
.stars li:nth-child(8) {left: 25%;top: 63%;}
.stars li:nth-child(9) {left: 27%;top: 17%;}
.stars li:nth-child(10) {left: 33%;top: 17%;}
.stars li:nth-child(11) {top: 45%;left: 29%;}
.stars li:nth-child(12) {left: 34%;top: 50%;}
.stars li:nth-child(13) {left: 35.4%;top: 50.3%;}
.stars li:nth-child(14) {left: 34.8%;top: 51%;}
.stars li:nth-child(15) {top: 58%;left: 33.5%;}
.stars li:nth-child(16) {left: 23.6%;bottom: 20%;}
.stars li:nth-child(17) {left: 32%;top: 17.5%;}
.stars li:nth-child(18) {left: 42%;top: 6%;}
.stars li:nth-child(19) {left: 42%;top: 18%;}
.stars li:nth-child(20) {left: 43.2%;top: 21%;}
.stars li:nth-child(21) {left: 45.5%;top: 25%;}
.stars li:nth-child(22) {left: 45%;bottom: 29%;}
.stars li:nth-child(23) {right: 46%;bottom: 33.2%;}
.stars li:nth-child(24) {right: 45.2%;bottom: 29.7%;}
.stars li:nth-child(25) {bottom: 26%;left: 55.4%;}
.stars li:nth-child(26) {bottom: 29.7%;left: 56.7%;}
.stars li:nth-child(27) {bottom: 33.7%;left: 57.4%;}
.stars li:nth-child(28) {left: 57%;top: 24%;}
.stars li:nth-child(29) {left: 62.5%;top: 12%;}
.stars li:nth-child(30) {left: 72%;top: 4%;}
.stars li:nth-child(31) {left: 79%;top: 16.5%;}
.stars li:nth-child(32) {left: 85%;top: 48%;}
.stars li:nth-child(33) {left: 42.4%;top: 9%;}
.stars li:nth-child(34) {left: 67%;top: 39%;}
.stars li:nth-child(35) {left: 74.5%;top: 25.5%;}
.stars li:nth-child(36) {left: 74.8%;top: 27.4%;}
.stars li:nth-child(37) {left: 78%;top: 24%;}
.stars li:nth-child(38) {left: 91.5%;top: 30.5%;}
.stars li:nth-child(39) {left: 95.5%;top: 29.5%;}
.stars li:nth-child(40) {left: 91.8%;top: 33.5%;}
.stars li:nth-child(41) {left: 96.8%;top: 39.8%;}
.stars li:nth-child(42) {left: 98.5%;top: 41.2%;}
.stars li:nth-child(43) {left: 90.5%;top: 47.5%;}
.stars li:nth-child(44){left: 80%;top: 54%;}
.stars li:nth-child(45) {left: 97%;top: 61%;}
.stars li:nth-child(46) {left: 77%;top: 61%;}
.stars li:nth-child(47) {left: 79.5%;top: 63.5%;}
.stars li:nth-child(48) {left: 71%;top: 73%;}
</style>
