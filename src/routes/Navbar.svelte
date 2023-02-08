<script>
    import Hamburger from './Hamburger.svelte'
    import Sidebar from './Sidebar.svelte'
    import logo from '$lib/images/logo-jejamuran-color.png'

    export let openSidebar = false
</script>

<Sidebar bind:open={openSidebar} />
<nav>
    <div class="menu-icon">
        <Hamburger bind:open={openSidebar} />
    </div>

    <div class="logo">
        <img src={logo} alt="Logo jejamuran" />
    </div>
</nav>

<style>
    nav {
        display: flex;
        padding: 8px 20px;
        position: relative;
        box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.12);
    }

    .menu-icon {
        display: grid;
        place-items: center;
    }

    .logo {
        margin-inline: auto;
    }
</style>