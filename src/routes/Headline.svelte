<script>
    export let title
    export let subtitle
    export let paddingTop
</script>

<div class="title" style:padding-top={paddingTop}>
    <h2>{title} <br> <span>{subtitle}</span></h2>
</div>

<style>
    .title {
        padding-top: 20px;
    }

    .title h2 {
        font-family: 'Yeseva One', cursive;
        font-size: 32px;
        line-height: 150%;
        color: #3d3d3d;
    }

    .title h2 span {
        color: var(--clr-brand);
    }
</style>