<script>
    import { onNavigate } from '$app/navigation';

    onNavigate((navigation) => {
        if (!document.startViewTransition) return;

        return new Promise(resolve => {
            document.startViewTransition(async () => {
                resolve();
                await navigation.complete;
            });
        });
    });
</script>

<div>
    <h1>qatar museums</h1>
</div>

<style>
   div {
       background-image: url(/popart.jpg);
       background-size: cover;
       background-repeat: no-repeat;
       background-position: center;
       width: 100vw;
       height: 100vh;
       position: absolute;
       top: 50%;
       left: 50%;
       transform: translate(-50%, -50%) scale(0);
       border-radius: 50%;
       overflow: hidden;
       animation: grow 3s forwards;
   }

   @keyframes grow {
       0% {
           transform: translate(-50%, -50%) scale(0);
       }
       100% {
           transform: translate(-50%, -50%) scale(1.5); 
       }
   }

     h1 {
        position: absolute;
        top: 26%;
        left: 31%;
        transform: rotate(9deg);
        font-size: 5em;
        font-weight: 100;
        width: 6em;
        text-align: center;
        -webkit-text-stroke: 0.5px var(--rose);
        z-index: 665;
   }
</style>
