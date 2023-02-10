<script>
    import Modal from './Modal.svelte'
    import Headline from './Headline.svelte'
    import mushrooms from './jamur.js'

    let showModal = false
    let modalData
    let modals = []
    mushrooms.forEach(() => {
        modals = [...modals, false]
    })

    const openModal = (e) => {
        const btn = e.target.closest('button')
        const index = btn.dataset.index
        modals[index] = true
    }
</script>

<section id="jenis" class="wrapper">
    <Headline title="Jenis-Jenis" subtitle="Jamur" paddingTop="30px" />

    <div class="list-container">
        <ul class="list">
            {#each mushrooms as {title, img, imgBig, desc}, i}
                <li class="list-item">
                    <button on:click={openModal} data-index={i}>
                        <div class="list-img">
                            <img src={img} alt={title}>
                        </div>

                        <div class="list-title">
                            <div class="triangle"></div>
                            <h3 class="title">{title}</h3>
                        </div>
                    </button>
                </li>

                <Modal modalData={{ title, imgBig, desc }} bind:showModal={modals[i]} />
            {/each}
        </ul>
    </div>

    <div class="video-container">
        <div class="video">
            <iframe src="https://www.youtube-nocookie.com/embed/X_zjCBjkj6w" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
        </div>

        <div class="desc">
            <p>
                Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua...
            </p>
        </div>
    </div>
</section>

<style>
    .wrapper {
        padding-inline: 16px;
    }

    .list-container {
        margin-top: 33px;
    }

    .list-container .list {
        list-style: none;
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 15px;
        row-gap: 25px;
    }

    .list-item button {
        background: none;
        border: none;
        width: 100%;
    }

    .list-img > img {
        margin-inline: auto;
    }

    .list-title .triangle {
        width: 12px;
        height: 12px;
        margin-inline: auto;
        clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
        position: relative;
    }

    .list-title .title {
        padding: 8px 0;
        text-align: center;
        border-radius: 6px;
        font-size: 14px;
        font-weight: 700;
        line-height: 20px;
        color: white;
    }

    .list-item:nth-child(4n+1) .list-title > *, .list-item:nth-child(4n) .list-title > * {
        background-color: var(--clr-accent);
    }

    .list-item:nth-child(4n+3) .list-title > *, .list-item:nth-child(4n+2) .list-title > * {
        background-color: var(--clr-brand);
    }

    .video-container {
        margin-top: 42px;
    }

    .video-container .video {
        aspect-ratio: 16/9;
    }

    .video-container .video iframe {
        width: 100%;
        height: 100%;
    }

    .video-container .desc {
        padding-block: 14px 24px;
    }

    .video-container .desc p {
        font-family: 'Poppins', sans-serif;
        font-weight: 400;
        font-size: 12px;
        line-height: 180%;
        color: #3D3D3D;
    }
</style>