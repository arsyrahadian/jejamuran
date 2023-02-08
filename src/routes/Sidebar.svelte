<script>
    import logo from '$lib/images/logo-jejamuran-color.png'

    export let open = false
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<aside class:open on:click|self={() => open = !open}>
    <div class="menu">
        <header>
            <span></span>
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
        position: absolute;
        width: 100%;
        height: 100%;
        left: -100%;
        z-index: 10;
        transition: left 0.3s ease-in-out
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
    }

    header span {
        width: 24px;
        height: 24px;
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