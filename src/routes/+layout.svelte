<script>
    import { onNavigate } from '$app/navigation';
    
    function delayNavigation() {
        return new Promise((resolve) => setTimeout(resolve, 100));
    }
    
    onNavigate(async (navigation) => {
        if (!document.startViewTransition) {
            await delayNavigation();
            return;
        }
    
        return new Promise((resolve) => {
            document.startViewTransition(async () => {
            await delayNavigation();
            resolve();
            await navigation.complete;
            });
        });
    });
    </script>

<div>
    <p>qatar museums</p>
</div>
<slot />
<style>
   div {
       background-image: url(/popart.jpg);
       background-size: cover;
       background-repeat: no-repeat;
       background-position: center;
       border-radius: 50%;
       height: 100vh;
       left: 50%;
       position: fixed;
       overflow: hidden;
       top: 50%;
       transform: translateX(-180%);
       view-transition-name: vi;
       width: 100vw;

    }
    
    @media (prefers-reduced-motion: no-preference) {
        :root::view-transition-group(vi) {
            animation: grow 3s forwards;
        }
    } 

   @keyframes grow {
       0% {
        transform: none;
        scale: 0;
        opacity: 0;
       }

       40%, 60% {
            opacity: 1;
            scale: 1.45;
       }

       99% {
            opacity: 0;  
            transform: none;
       }

       100% {
            transform: translateX(-180%)
       }
   }

     p {
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
