<script>
    import { fade } from 'svelte/transition'
    import Navbar from '../Navbar.svelte'
    import MushroomList from '../MushroomList.svelte'
    import Pricelist from '../Pricelist.svelte'

    let openSidebar;
</script>

{#if openSidebar}
    <div class="backdrop" transition:fade={{ duration: 300 }}></div>
{/if}
<Navbar bind:openSidebar />

<main>
    <MushroomList />
    <Pricelist />
</main>

<style>
    main {
        background-color: #fafafa;
    }

    main :global(.wrapper) {
        background-color: white;
    }

    .backdrop {
        width: 100vw;
        height: 100vh;
        position: fixed;
        z-index: 5;
        background: rgba(0, 0, 0, 0.3);
    }
</style>