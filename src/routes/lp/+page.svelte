<script>
    import Navbar from '../Navbar.svelte'
    import { fade } from 'svelte/transition'

    let openSidebar;
</script>

{#if openSidebar}
    <div class="backdrop" transition:fade={{ duration: 300 }}></div>
{/if}
<Navbar bind:openSidebar />

<main>

</main>

<style>
    main {
        margin-inline: 16px;
        background-color: #fafafa;
    }

    .backdrop {
        width: 100vw;
        height: 100vh;
        position: fixed;
        z-index: 5;
        background: rgba(0, 0, 0, 0.15);
    }
</style>