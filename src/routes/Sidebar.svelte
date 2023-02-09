<script>
    import logo from '$lib/images/logo-jejamuran-color.png'

    export let open = false
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<aside class:open on:click|self={() => open = !open}>
    <div class="menu">
        <header>
            <button on:click={() => open = !open}>
                <svg xmlns="http://www.w3.org/2000/svg" class="icon icon-tabler icon-tabler-plus" width="24" height="24" viewBox="0 0 24 24" stroke-width="1" stroke="#3d3d3d" fill="none" stroke-linecap="round" stroke-linejoin="round">
                    <path stroke="none" d="M0 0h24v24H0z" fill="none"/>
                    <line x1="12" y1="5" x2="12" y2="19" />
                    <line x1="5" y1="12" x2="19" y2="12" />
                </svg>
            </button>
            <div class="logo">
                <img src={logo} alt="Logo Jejamuran" />
            </div>
        </header>

        <nav>
            <ul class="menu-list">
                <li class="menu-item">
                    <a href="#jenis">Jenis-Jenis Jamur</a>
                </li>
                <li class="menu-item">
                    <a href="#paket">Paket Agrowisata</a>
                </li>
                <li class="menu-item">
                    <a href="#kontak">Hubungi Kami</a>
                </li>
            </ul>
        </nav>
    </div>
</aside>

<style>
    aside {
        position: fixed;
        width: 100%;
        height: 100%;
        left: -100%;
        z-index: 15;
        transition: left 0.3s ease-in;
    }

    .open {
        left: 0;
    }

    .menu {
        width: 80%;
        height: 100%;
        padding: 8px 20px;
        background-color: white;
    }

    header {
       display: flex;
       align-items: center;
    }

    header button {
        background: none;
        border: none;
        cursor: pointer;
    }

    header svg {
        scale: 1.3;
        transform: rotate(45deg);
    }

    header .logo {
        margin-inline: auto;
    }

    .menu-list {
        margin-top: 30px;
        list-style: none;
    }

    .menu-item > a {
        text-decoration: none;
        color: #3d3d3d;
        font-weight: 600;
        display: block;
        padding: 8px 8px 8px 4px;
    }
</style>