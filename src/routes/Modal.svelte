<script>
    import { afterUpdate } from 'svelte'

    export let modalData
    export let showModal

    const {title, imgBig, desc} = modalData

    let first = true
    let backdrop
    let modal
    let initialHeight
    let display
    let para
    let expandBtn
    let btnText = 'Baca Selengkapnya'
    let isExpanded = false

    const closeModal = () => {
        first = true
        backdrop.classList.add('closing')
        modal.style.removeProperty('--mh-initial')
        if (isExpanded) shrink()
    }

    const expand = () => {
        const innerModal = expandBtn.closest('.inner-modal')
        display = 'block'
        isExpanded = true

        innerModal.style.overflowY = 'scroll'
        para.style.display = display
        modal.classList.add('modal-expand')
        btnText = 'Tampilkan Sedikit'
        innerModal.classList.add('expand')
    }

    const shrink = () => {
        const innerModal = expandBtn.closest('.inner-modal')
        display = '-webkit-box'
        isExpanded = false

        modal.classList.add('modal-shrink')
        innerModal.style.overflowY = 'hidden'
    }

    const handleClick = () => {
        if (!isExpanded) {
            expand()
        } else {
            shrink()
        }
    }

    const handleBackdrop = e => {
        const target = e.target

        if (target.classList.contains('closing')) {
            target.classList.remove('closing')
            showModal = false
        }
    }

    const handleModal = e => {
        const target = e.target

        if (target.classList.contains('modal-shrink')) {
            para.style.display = display
            btnText = 'Baca Selengkapnya'

            target.classList.remove('modal-expand')
            target.classList.remove('modal-shrink')
        }
    }

    afterUpdate(() => {
        if (showModal && first) {
            first = false
            initialHeight = `${modal.offsetHeight}px`
            modal.style.setProperty('--mh-initial', initialHeight)
        }
    })
</script>

<!-- svelte-ignore a11y-click-events-have-key-events -->
<div class="backdrop opening" bind:this={backdrop} on:click|self={closeModal} on:animationend={handleBackdrop} style:display={showModal ? 'grid' : 'none'}>
    <div class="modal" bind:this={modal} on:animationend={handleModal}>
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
            <p bind:this={para}>{desc}</p>
            <button bind:this={expandBtn} on:click={handleClick}>{btnText}</button>
        </section>
    </div>
</div>

<style>
    .backdrop {
        width: 100vw;
        height: 100vh;
        position: fixed;
        inset: 0;
        display: grid;
        place-items: center;
        padding: 0 16px;
        background: rgba(0, 0, 0, 0.3);
        z-index: 30;
    }

    :global(.opening) {
        animation: opening 0.3s ease-in;
    }

    @keyframes -global-opening {
        from {
            opacity: 0
        }
        to {
            opacity: 1
        }
    }

    :global(.closing) {
        animation: closing 0.3s ease-in;
        animation-fill-mode: forwards;
    }

    @keyframes -global-closing {
        0% {
            opacity: 1
        }
        100% {
            opacity: 0
        }
    }

    .modal {
        width: 100%;
        max-width: 400px;
        display: flex;
        flex-direction: column;
        border-radius: 12px;
        background: white;
        overflow: hidden;
    }
    
    :global(.modal-expand) {
        animation: expand 0.3s ease-in;
    }

    @keyframes -global-expand {
        0% {
            max-height: var(--mh-initial)
        }
        100% {
            max-height: 100%
        }
    }
    
    :global(.modal-shrink) {
        animation: shrink 0.3s ease-in;
    }

    @keyframes -global-shrink {
        0% {
            max-height: 100%
        }
        100% {
            max-height: var(--mh-initial)
        }
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
        max-height: 55vh;
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