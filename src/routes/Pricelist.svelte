<script>
    import Headline from './Headline.svelte'
    import Accordion from './Accordion.svelte'
    import paket from './paket.js'
</script>

<div class="wrapper">
    <div class="headline-container">
        <Headline title="Paket Agrowisata" subtitle="Jejamuran" />
    </div>

    {#each paket as p}
        <Accordion accent={p.accent} paket={p} />
    {/each}
</div>

<style>
    .wrapper {
        margin-top: 16px;
        padding-bottom: 20px;
    }

    .wrapper .headline-container {
        padding-inline: 16px;
    }
</style>