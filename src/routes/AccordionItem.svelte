<script>
    import { slide } from 'svelte/transition'
    import { cubicIn } from 'svelte/easing'

    export let accent
    export let details
</script>

{#each details as detail}
    <div class="accordion-content" class:accent transition:slide={{ duration: 300, easing: cubicIn }}>
        <div class="card-wrapper">
            <div class="card">
                <div class="card-header">
                    <h3>{detail.title}</h3>
                    {#if detail.subtitle}
                        <p>{detail.subtitle}</p>
                    {/if}

                    {#each detail.prices as price}
                        <div class="price">
                            {price.price}<span>{price.sub || ''}</span>
                        </div>
                    {/each}
                </div>
                <div class="card-content">
                    {#each detail.content as content}
                        {#if content.type === 'column'}
                            <div class="content col-content">
                                <h3>{content.title}</h3>
                                <p>{content.desc}</p>
                            </div>
                        {:else if content.type === 'row'}
                            <div class="content row-content">
                                <h3>{content.title}</h3>
                                {#if Array.isArray(content.desc)}
                                    <div>
                                        <ul>
                                            {#each content.desc as desc}
                                                <li>{desc}</li>
                                            {/each}
                                        </ul>
                                    </div>
                                {:else}
                                    <p>{content.desc}</p>
                                {/if}
                            </div>
                        {/if}
                    {/each}
                    
                    {#if detail.disclaimer}
                        <p class="disclaimer">{detail.disclaimer}</p>
                    {/if}
                </div>
            </div>
        </div>
    </div>
{/each}

<style>
    .accordion-content {
        margin-block: 5px 20px;
        padding-inline: 16px;
    }

    .card-wrapper > *:not(:first-child) {
        margin-top: 20px;
    }

    .card-wrapper .card {
        padding-inline: 16px;
        border: 2px solid var(--clr-brand);
        border-radius: 6px;
    }

    .accent .card-wrapper .card {
        border-color: var(--clr-accent);
    }

    .card-header {
        padding-block: 17px 20px;
        border-bottom: 1px solid #eaeaea;
        display: flex;
        flex-direction: column;
        text-align: center;
    }

    .card-header h3 {
        font-family: 'Poppins', sans-serif;
        font-weight: 700;
        font-size: 20px;
        line-height: 150%;
        text-transform: uppercase;
        color: var(--clr-brand);
    }

    .accent .card-header h3 {
        color: var(--clr-accent);
        margin-bottom: 5px;
    }

    .card-header p {
        font-weight: 600;
        font-size: 14px;
        line-height: 150%;
        color: #3d3d3d;
    }

    .card-header .price {
        padding: 8px;
        background-color: var(--clr-brand);
        border-radius: 24px;
        font-weight: 600;
        font-size: 18px;
        line-height: 150%;
        color: white;
    }

    .accent .card-header .price {
        background-color: var(--clr-accent);
    }

    .card-header .price span {
        font-size: 12px;
        line-height: 18px;
    }

    .card-header .price:first-of-type {
        margin-top: 15px;
    }

    .card-header .price:not(:first-of-type) {
        margin-top: 20px;
    }

    .card-content {
        padding-block: 20px 25px;
    }

    .card-content > .content:not(:first-child) {
        margin-top: 20px;
    }

    .card-content > .col-content {
        display: flex;
        justify-content: space-between;
    }

    .card-content > .row-content > *:not(:first-child) {
        margin-top: 5px;
    }

    .card-content > .content h3 {
        font-weight: 600;
        font-size: 14px;
        line-height: 150%;
        color: #3d3d3d;
    }
    .card-content > .content p, .card-content > .content div {
        font-weight: 500;
        font-size: 14px;
        line-height: 150%;
        color: #898989;
    }

    .content ul li {
        margin-left: 25px;
    }

    .card-content > p.disclaimer {
        margin-top: 15px;
        font-weight: 500;
        font-size: 14px;
        line-height: 21px;
        color: var(--clr-brand);
    }

    .accent .card-content > p.disclaimer {
        color: var(--clr-brand);
    }
</style>