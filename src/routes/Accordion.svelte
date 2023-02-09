<script>
    import AccordionItem from './AccordionItem.svelte'

    export let accent = false
    export let paket

    let isOpen = false
    const toggle = () => isOpen = !isOpen
</script>

<div class="accordion-container">
    <div class="accordion" class:accent>
        <button class="accordion-header" on:click={toggle}>
            <h2>{paket.name}</h2>
            <div class="chevron">
                <svg width="14" height="8" viewBox="0 0 14 8" fill="none" xmlns="http://www.w3.org/2000/svg" class:open={isOpen}>
                    <path d="M1 1L7 7L13 1" stroke="white" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
                </svg>
            </div>
        </button>
        {#if isOpen}
            <AccordionItem {accent} details={paket.detail} />
        {/if}
    </div>
</div>

<style>
    .accordion-container {
        margin-top: 10px;
        border-bottom: 1px solid #eaeaea;
    }

    .accordion {
        border-bottom: 1px solid #eaeaea;
    }

    .accordion .accordion-header {
        width: 100%;
        display: flex;
        justify-content: space-between;
        align-items: center;
        background: none;
        border: none;
        padding: 16px;
    }

    .accordion .accordion-header h2 {
        font-weight: 600;
        font-size: 16px;
        line-height: 150%;
        text-transform: uppercase;
    }

    .accordion .accordion-header .chevron {
        width: 32px;
        height: 32px;
        display: grid;
        place-items: center;
        background-color: var(--clr-brand);
        border-radius: 50%;
    }

    .accordion.accent .accordion-header .chevron {
        background-color: var(--clr-accent);
    }

    .chevron svg {
        transition: transform 0.3s ease-in;
    }

    .chevron svg.open {
        transform: rotate(-180deg);
    }
</style>