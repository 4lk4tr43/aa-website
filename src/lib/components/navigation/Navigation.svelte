<script>
	import Navigation from '$lib/components/navigation/desktop/Navigation.svelte'

	const logo = '/logo.png'
	const routes = [
		{title: 'Home', href: '/'},
		{title: 'Features', href: '/features'},
		{title: 'Prices', href: '/prices'},
	]
</script>

<Navigation {logo} {routes}/>