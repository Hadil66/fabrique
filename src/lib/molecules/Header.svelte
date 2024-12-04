<script>
	import { onMount } from 'svelte';

</script>

<header bind:this={header} class="headie-one">
    <h1>
        qatar museums
    </h1>
</header> 

<style>
        @font-face {
            font-family: "SuperWoobly";
            src: url(/fonts/SuperWoobly-8MJlz.ttf);
        }

        header {
            align-items: center;
            background: #c60000;
            display: flex;
            flex-direction: column;
            height: 100vh;
            justify-content: center;
            left: 0;
            position: fixed;
            /* top: 0; */
            width: 100%;
            z-index: 369;
        }


        h1 {
            color: #fff;
            font-family: "SuperWoobly";
            font-size: 5em;
            text-align: center;
            text-transform: uppercase;
        }

        @media (max-width:480px) {
            h1 {
                font-size: 3em;
            }
        }
</style>