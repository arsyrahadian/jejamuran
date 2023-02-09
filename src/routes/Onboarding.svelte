<script>
    import onboarding_img from '$lib/images/onboarding-img.png'
    import logo from '$lib/images/logo-jejamuran.png'
</script>

<div class="wrapper">
    <img src={onboarding_img} class="main-img" alt="Selamat datang" />

    <div class="title">
        <section class="header">
            <img src={logo} alt="Logo Jejamuran" />
            <h1 class="ff-brand">Mengenal <br /> Jamur</h1>
            <p>Ayo berkenalan dengan beragam jamur dan manfaatnya</p>
        </section>

        <a href="/lp" class="start-btn">
            <svg
                width="24"
                height="24"
                viewBox="0 0 24 24"
                fill="none"
                xmlns="http://www.w3.org/2000/svg"
            >
                <path
                    d="M9 6L15 12L9 18"
                    stroke="white"
                    stroke-width="2"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                />
            </svg>
        </a>
    </div>
</div>

<style>
    .wrapper {
        position: relative;
    }

    .wrapper .main-img {
        margin-inline: auto;
        width: 100%;
    }

    .wrapper .title {
        display: flex;
        flex-direction: column;
        justify-content: flex-end;
        align-items: center;
        position: absolute;
        inset: 0;
        padding: 0 16px;
        border-radius: 24px;
        text-align: center;
        color: white;
        background: linear-gradient(
            0deg,
            #f27e01 10.32%,
            rgba(242, 126, 1, 0) 83.22%
        );
    }

    .wrapper .title .header {
        text-align: center;
    }

    .wrapper .title .header h1 {
        font-size: 40px;
        line-height: 46px;
    }

    .wrapper .title .header p {
        font-size: 14px;
        line-height: 180%;
    }

    .wrapper .title .header img {
        margin: 0 auto;
    }

    .wrapper .title .header > *:not(:last-child) {
        margin-bottom: 20px;
    }

    .start-btn {
        width: 74px;
        height: 74px;
        display: grid;
        place-items: center;
        position: relative;
        border-radius: 50%;
        background-color: #f27e01;
        bottom: calc(-74px / 2);
    }

    .start-btn svg {
        color: white;
    }
</style>
