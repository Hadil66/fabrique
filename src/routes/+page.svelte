<script>
    export let data;
    console.log(data); // Hiermee kun je zien hoe de API-respons eruitziet

    import Navbar from '$lib/navbar.svelte';
</script>

<Navbar />


{#each data.artObjects as art}
    <ul>
        <li>
            <h2>{art.title}</h2>
            <img src={"https://fdnd-agency.directus.app/assets/" + art.image} alt={art.title} />
        </li>
    </ul>
{/each}

