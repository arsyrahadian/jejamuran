<script>
    import { fade } from 'svelte/transition'
    import { cubicInOut } from 'svelte/easing'
    import { onMount } from 'svelte'

    export let modalData
    export let showModal

    const {title, imgBig, desc} = modalData
    const closeModal = () => {
        showModal = false
    }

    let modal
    let initialHeight = '361px'
    let display = '-webkit-box'
    let btnText = 'Baca Selengkapnya'
    const handleClick = e => {
        const btn = e.target
        const para = btn.previousElementSibling
        const innerModal = para.closest('.inner-modal')

        if (display === '-webkit-box') {
            display = 'block'
            para.style.display = display
            modal.style.maxHeight = '100%'
            btnText = 'Tampilkan Sedikit'
        } else {
            innerModal.scrollTop = 0
            modal.style.maxHeight = initialHeight
            setTimeout(() => {
                display = '-webkit-box'
                para.style.display = display
                btnText = 'Baca Selengkapnya'
            }, 400);
        }
    }

    onMount(() => {
        modal = document.querySelector('.modal')
    })
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<div class="backdrop" on:click|self={closeModal} transition:fade={{ duration: 300, easing: cubicInOut }}>
    <div class="modal">
        <header class="modal-header">
            <img src={imgBig} alt={title}>
            <button on:click={closeModal}>
                <svg width="14" height="14" viewBox="0 0 14 14" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <path d="M13 1L1 13M1 1L13 13" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
            </button>
        </header>
        <section class="inner-modal">
            <h4>{title}</h4>
            <p>{desc}</p>
            <button on:click={handleClick}>{btnText}</button>
        </section>
    </div>
</div>

<style>
    .backdrop {
        width: 100%;
        height: 100%;
        position: fixed;
        inset: 0;
        display: grid;
        place-items: center;
        padding: 0 16px;
        background: rgba(0, 0, 0, 0.3);
        z-index: 30;
    }

    .modal {
        width: 100%;
        max-height: 361px;
        border-radius: 12px;
        background: white;
        overflow: hidden;
        transition: max-height 0.3s ease-in;
    }

    .modal header {
        position: relative;
    }

    .modal header img {
        width: 100%;
    }

    .modal .modal-header button {
        position: absolute;
        top: 22px;
        right: 22px;
        background: none;
        border: none;
    }

    .modal .inner-modal {
        padding: 20px 16px;
        max-height: 65vh;
        overflow-y: scroll;
        scroll-behavior: smooth;
    }

    .modal .inner-modal h4 {
        font-family: 'Yeseva One', cursive;
        font-size: 18px;
        font-weight: 400;
        line-height: 20px;
        letter-spacing: 0.01em;
    }

    .modal .inner-modal p {
        display: -webkit-box;
        -webkit-line-clamp: 3;
        -webkit-box-orient: vertical;
        margin-block: 10px;
        overflow: hidden;
    }

    .modal .inner-modal button {
        background: none;
        border: none;
        cursor: pointer;
        display: block;
        width: 100%;
        font-family: 'Poppins', sans-serif;
        font-weight: 600;
        font-size: 12px;
        line-height: 180%;
        color: #F27E01;
    }
</style>