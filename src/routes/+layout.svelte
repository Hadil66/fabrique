<script>
    import { onNavigate} from '$app/navigation';

    onNavigate((navigation) => {
     if (!document.startViewTransition) return
 
     return new Promise(resolve => {
         document.startViewTransition(async () => {
             resolve()
             await navigation.complete
         })
     })
    })
 </script>

<main>
    <h1>qatar museums</h1>

</main>

<style>
   main{
       background-image: url('/popart.jpg');
       background-size: cover;
       background-repeat: no-repeat;
       background-position: center;
       height: 100vh;
       width: 220vh;
   }

   h1 {
        position: absolute;
        top: 26%;
        left: 31%;
        animation: pop 0.5s;
        transform: rotate(9deg);
        font-size: 5em;
        font-weight: 100;
        width: 6em;
        text-align: center;
        -webkit-text-stroke: 1px var(--rose);
   }

   @keyframes pop {
       0% {opacity: 0;}
       100% {opacity: 1;}

   }

   :root::view-transition-old(root) {
    main {
        display: none;
    }
}

:root::view-transition-new(root) {
    main {
        display: block;
    }
}
</style>