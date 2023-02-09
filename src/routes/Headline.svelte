<script>
    export let title
    export let subtitle
    export let marginTop
</script>

<div class="title" style:margin-top={marginTop}>
    <h2>{title} <br> <span>{subtitle}</span></h2>
</div>

<style>
    .title {
        margin-top: 20px;
    }

    .title h2 {
        font-family: 'Yeseva One';
        font-size: 32px;
        line-height: 150%;
        color: #3d3d3d;
    }

    .title h2 span {
        color: var(--clr-brand);
    }
</style>