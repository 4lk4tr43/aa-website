<script>
    import Footer from "$lib/components/footer/Footer.svelte";
    import Navigation from '$lib/components/navigation/Navigation.svelte'
</script>

<header>
    <Navigation/>
</header>

<main>
    <div>
        <slot/>
    </div>
</main>

<footer>
    <div>
        <Footer/>
    </div>
</footer>

<style>
    :root {
        --background-1: hsl(0, 2%, 19%);
        --selected-1: hsl(300, 20%, 32%);
        --text-1: hsl(0, 2%, 88%);
    }

    :global(html, body) {
        margin: 0;
        padding: 0;
        min-height: 100vh;
    }

    :global(body) {
        overflow: auto;
        position: relative;
    }

    footer, main {
        display: flex;
        justify-content: center;
    }

    footer > div, main > div {
        max-width: 50rem;
    }

    footer {
        bottom: 0;
        min-width: 100vw;
        position: absolute;
        background: var(--background-1);
        color: var(--text-1);
    }
</style>
