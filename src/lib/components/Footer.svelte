<script>
    import Logo from "./Logo.svelte";
    /**
     * @type {Boolean}
     */
    export let escape;

    $: alignment = escape ? "space-between" : "flex-end";
</script>

<!-- <hr/> -->
<footer style="justify-content: {alignment}">
    {#if escape}
        <a href="/"><i class="bi bi-arrow-left-circle" /> &nbsp; Go Back Home</a
        >
    {/if}
    <!-- <p class="muted">&copy; Gravatar Lookup 2023</p> -->
    <Logo />
</footer>

<style>
    footer {
        width: 100%;
        display: flex;
        flex-direction: row;
        align-items: center;
        align-content: center;
    }
</style>
