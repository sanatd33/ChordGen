<script>
    let keyProps = {class:[$$restProps.class]}
</script>

<!-- svelte-ignore a11y-no-static-element-interactions -->
<key on:mousedown
    on:mouseup
    on:click
    {...keyProps}>
    <slot/>
</key>

<style>
    .white{
        width: 5rem;
        cursor: pointer;
        position: relative;
        height: 20rem;
        border-radius: 10px;
        border: 1px solid #000;
        background-color: #fff;
        display: inline-block;
    }
    .black{
        cursor: pointer;
        position: relative;
        width: 2rem;
        height: 13rem;
        border-radius: 5px;
        border-top-left-radius: 0;
        border-top-right-radius: 0;
        background-color: #000;
        z-index: 2;
        margin: 0 -20px 0 -20px;
        display: inline-block;
        border: 1px solid #fff;
        bottom:7rem
    }
</style>