<script>
    import {page} from '$app/stores'
    import Footer from '$lib/components/Footer.svelte';
    import Top from '$lib/components/Top.svelte';
</script>

<svelte:head>
    <title>Gravatar Look Up | {$page.error?.message}</title>
    <meta name="robots" content="noindex nofollow">
</svelte:head>
<main>
    <!-- <Top/> -->
    <h1>Error: {$page.status}</h1>
    <p>{$page.error?.message}</p>
    <Footer escape={true}/>
</main>