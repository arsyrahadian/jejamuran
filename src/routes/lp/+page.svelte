<script>
    import { fade } from 'svelte/transition'
    import Navbar from '../Navbar.svelte'
    import MushroomList from '../MushroomList.svelte'

    let openSidebar;
</script>

{#if openSidebar}
    <div class="backdrop" transition:fade={{ duration: 300 }}></div>
{/if}
<Navbar bind:openSidebar />

<main>
    <MushroomList />
</main>

<style>
    main {
        background-color: #fafafa;
    }

    main :global(.wrapper) {
        padding-inline: 16px;
        background-color: white;
    }

    .backdrop {
        width: 100vw;
        height: 100vh;
        position: fixed;
        z-index: 5;
        background: rgba(0, 0, 0, 0.3);
    }

    main :global(.wrapper > .title) {
        margin-top: 20px;
    }

    main :global(.wrapper > .title h2) {
        font-family: 'Yeseva One';
        font-size: 32px;
        line-height: 150%;
        color: #3d3d3d;
    }

    main :global(.wrapper > .title h2 span) {
        color: var(--clr-brand);
    }
</style>