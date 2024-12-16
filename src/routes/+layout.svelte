<div class="full-door">
<div class="door-frame">
    <div class="door"></div>
</div>
</div>

<slot/>

<style>
    .full-door {
        z-index: 100;
        position: relative;
	background-color: #2d2d2d;
	display: flex;
	justify-content: center;
	align-items: center;
	height: 100vh;
	margin: 0;
	font-family: "Arial", sans-serif;
}

.door-frame {
	width: 200px;
	height: 400px;
background-color: transparent;
	border: 15px solid #ff0;
	border-radius: 2px;
	position: relative;
	perspective: 800px; /* Adding perspective for 3D effect */
}

.door {
	width: 100%;
	height: 100%;
	background-color: #8b4513; /* Brown door */
	position: absolute;
	left: 0;
	top: 0;
	transform-origin: left; /* Pivot the door from the left side */
	transform: rotateY(0deg);
	transition: transform 2s ease-in-out;
}

.door::before {
	content: "";
	position: absolute;
	width: 15px;
	height: 40px;
	background-color: #222;
	border-radius: 20%;
	right: 20px;
	top: 50%;
	transform: translateY(-50%);
}

.door-frame:hover .door {
	transform: rotateY(-120deg); /* Swing open to 120 degrees */
}

</style>