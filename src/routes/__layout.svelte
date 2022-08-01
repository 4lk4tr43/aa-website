<script>
	import Navigation from '$lib/components/navigation/Navigation.svelte';
</script>

<header>
	<Navigation/>
</header>

<main>
	<slot/>
</main>

<footer>
	Footer
</footer>

<style>
	:global(html, body) {
		margin: 0;
		padding: 0;
	}

	:root {
		--background-1: hsl(0, 2%, 19%);
		--selected-1: hsl(300, 20%, 32%);
		--text-1: hsl(0, 2%, 88%);
	}
</style>