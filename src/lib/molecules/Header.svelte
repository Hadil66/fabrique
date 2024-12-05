<!-- <script>
	import { onMount } from 'svelte';
	import { cubicOut } from 'svelte/easing';

	let scrollY = 0; 
	let progress = 0; 

	onMount(() => {
		const onScroll = () => {
			scrollY = window.scrollY;
			const maxScroll = window.innerHeight * 0.9; 
			progress = Math.min(scrollY / maxScroll, 1); 
		};

		window.addEventListener('scroll', onScroll);
	});
</script>

<header class="headie-one"
    style="
        background-position: 50% calc(100% * {progress});
        height: calc(100vh - (90vh * {progress}));
    "
>
	<h1
		style="font-size: calc(5rem - (3rem * {progress}))"
    >
		Qatar Museums
	</h1>
</header>

<style>
	.headie-one {
		align-items: center;
        background-color: #c60000;
		display: flex;
		flex-direction: column;
		justify-content: center;
		position: fixed;
		top: 0;
		width: 100%;
		z-index: 369;
	}

	h1 {
		color: white;
		font-family: "SuperWoobly", sans-serif;
		text-align: center;
		text-transform: uppercase;
	}
</style> -->


<header>
	<h1>
		Qatar Museums
	</h1>
</header>
<div class="drip">
    <div id="ric-flair-drip"></div>
    <div id="drip-too-hard"></div>
    <div id="drip-or-drown"></div>
</div>


<style>
	header {
		align-items: center;
        animation: headie-one;
        animation-timeline: scroll();
        animation-range: 0vh 90vh;
        background-color: #c60000;
		display: flex;
		flex-direction: column;
		justify-content: center;
		position: fixed;
		top: 0;
		width: 100%;
		z-index: 369;
	}

	h1 {
		color: white;
		font-family: "SuperWoobly";
		text-align: center;
		text-transform: uppercase;
	}

    @keyframes headie-one {
        from {
            background-position: 50% 0;
		    height: 100vh;
            font-size: 2.5em;
        }
        to {
            background-position: 50% 100%;
            height: 10vh;
            font-size: 1em;
        }
    }
    </style>