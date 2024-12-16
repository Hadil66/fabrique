<script>
	import { onNavigate } from '$app/navigation'

	onNavigate((navigation) => {
		if (!document.startViewTransition) return

		return new Promise((resolve) => {
			document.startViewTransition(async () => {
				resolve()
				await navigation.complete
			})
		})
	})
</script>

<div > 
    <img id="stripe" src="/stripe.png" alt="stripeImg">
</div>

<slot/>

<style>
    @keyframes scale-up {
        from {
            visibility: hidden; /* Change to hidden if you want to animate visibility */
            transform: perspective(400px) translateZ(1px);
            background: url(/static/stripe.png) center no-repeat; 
            background-size: contain;
        }

        to {
            visibility: visible; /* Make it visible at the end of the animation */
            transform: perspective(1px) translateZ(1px);
            background: url(/static/stripe.png) center no-repeat; 
            background-size: contain;
        }
    }

    @keyframes scale-down {
        from {
            visibility: visible; /* Make it visible at the end of the animation */
            transform: perspective(1px) translateZ(1px);
            background: url(/static/stripe.png) center no-repeat; 
            background-size: contain;
        }

        to {
            visibility: hidden; /* Change to hidden if you want to animate visibility */
            transform: perspective(400px) translateZ(1px);
            background: url(/static/stripe.png) center no-repeat; 
            background-size: contain;
        }
    }

    @keyframes spin {
        to {
            transform: rotate(1turn);
        }
    }

    #stripe {
        position: absolute;
        top: calc(50% - 50px);
        left: calc(50% - 50px);
        width: 100px;
        height: 100px;
        z-index: -1;
        view-transition-name: moveImg;
    }  

    :root::view-transition-old(moveImg){
        animation: 0.5s linear both scale-up;
    }

    :root::view-transition-new(moveImg) {
        animation: 0.5s linear both scale-down;
        animation-delay: 0.5s;
    }
    
    :root::view-transition-old(root){
        animation-name: spin;
        animation-duration: 1s;
        animation-timing-function: linear;
        animation-fill-mode: both;
        animation-play-state: running;
    }
    :root::view-transition-new(root) {
        animation-name: spin;
        animation-duration: 1s;
    }
</style>