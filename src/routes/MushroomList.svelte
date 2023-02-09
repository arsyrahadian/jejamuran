<script>
    import jamurKancing from '$lib/images/icon-jamur-kancing.png'
    import jamurPortabello from '$lib/images/icon-jamur-portabello.png'
    import jamurTiram from '$lib/images/icon-jamur-tiram.png'
    import jamurMerang from '$lib/images/icon-jamur-merang.png'
    import jamurKuping from '$lib/images/icon-jamur-kuping.png'
    import jamurNameko from '$lib/images/icon-jamur-nameko.png'
    import jamurMonkeyhead from '$lib/images/icon-jamur-monkeyhead.png'
    import jamurLingzhi from '$lib/images/icon-jamur-lingzhi.png'

    import jamurKancingBig from '$lib/images/detail-jamur-kancing.png'
    import jamurKupingBig from '$lib/images/detail-jamur-kuping.png'
    import jamurLingzhiBig from '$lib/images/detail-jamur-lingzhi.png'

    import Modal from './Modal.svelte'
    import Headline from './Headline.svelte'

    const mushrooms = [
        {
            'title': 'Jamur Kancing',
            'img': jamurKancing,
            'imgBig': jamurKancingBig,
            'desc': 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam'
        },
        {
            'title': 'Jamur Portabello',
            'img': jamurPortabello,
            'imgBig': jamurKupingBig,
            'desc': 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam'
        },
        {
            'title': 'Jamur Tiram',
            'img': jamurTiram,
            'imgBig': jamurKupingBig,
            'desc': 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam'
        },
        {
            'title': 'Jamur Merang',
            'img': jamurMerang,
            'imgBig': jamurKupingBig,
            'desc': 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam'
        },
        {
            'title': 'Jamur Kuping',
            'img': jamurKuping,
            'imgBig': jamurKupingBig,
            'desc': 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam'
        },
        {
            'title': 'Jamur Nameko',
            'img': jamurNameko,
            'imgBig': jamurKupingBig,
            'desc': 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam'
        },
        {
            'title': 'Jamur Monkeyhead',
            'img': jamurMonkeyhead,
            'imgBig': jamurKupingBig,
            'desc': 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam'
        },
        {
            'title': 'Jamur Lingzhi',
            'img': jamurLingzhi,
            'imgBig': jamurLingzhiBig,
            'desc': 'Sed ut perspiciatis unde omnis iste natus error sit voluptatem accusantium doloremque laudantium, totam rem aperiam, eaque ipsa quae ab illo inventore veritatis et quasi architecto beatae vitae dicta sunt explicabo. Nemo enim ipsam voluptatem quia voluptas sit aspernatur aut odit aut fugit, sed quia consequuntur magni dolores eos qui ratione voluptatem sequi nesciunt. Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet, consectetur, adipisci velit, sed quia non numquam eius modi tempora incidunt ut labore et dolore magnam aliquam quaerat voluptatem. Ut enim ad minima veniam, quis nostrum exercitationem ullam'
        },
    ]

    let showModal = false
    let modalData

    const openModal = (data) => {
        modalData = data
        showModal = true
    }
</script>

<section class="wrapper">
    <Headline title="Jenis-Jenis" subtitle="Jamur" paddingTop="30px" />

    <div class="list-container">
        <ul class="list">
            {#each mushrooms as {title, img, imgBig, desc}}
                <li class="list-item">
                    <button on:click={() => openModal({title, imgBig, desc})}>
                        <div class="list-img">
                            <img src={img} alt={title}>
                        </div>

                        <div class="list-title">
                            <div class="triangle"></div>
                            <h3 class="title">{title}</h3>
                        </div>
                    </button>
                </li>

            {/each}
            {#if showModal}
                <Modal bind:modalData bind:showModal />
            {/if}
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
    }

    .list-img > img {
        margin-inline: auto;
    }

    .list-title .triangle {
        width: 12px;
        height: 12px;
        margin-inline: auto;
        clip-path: polygon(50% 0%, 0% 100%, 100% 100%);
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

    .video-container .video iframe {
        width: 100%;
        height: 182px;
    }

    .video-container .desc {
        padding-block: 14px 24px;
    }

    .video-container .desc p {
        font-family: 'Poppins';
        font-weight: 400;
        font-size: 12px;
        line-height: 180%;
        color: #3D3D3D;
    }
</style>