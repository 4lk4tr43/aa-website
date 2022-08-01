<script>
	import {page} from '$app/stores'

	export let routes
	export let logo

	let path
	page.subscribe(page => { path = page.url.pathname })

	function isRouteSelected(pathname, href) {
		return href === pathname || (href !== '/' && pathname.startsWith(href))
	}
</script>

<nav>
	{#if logo}
		<a class="logo" href="/">
			<img alt="logo" src={logo}>
		</a>
	{/if}

	{#if routes}
		<ul class="navigation">
			{#each routes as {href, title}}
				<li class:selected={isRouteSelected(path, href)}>
					<a {href}>{title}</a>
				</li>
			{/each}
		</ul>
	{/if}

	<ul class="controls">
		<li>
			<input type="search" placeholder="Search...">
		</li>
	</ul>
</nav>

<style>
	nav {
		background: var(--background-1);
		color: var(--text-1);

		height: 3rem;

		display: grid;
		grid-template-columns: .5fr 1fr .5fr;
		align-items: stretch;
	}

	ul {
		margin: 0;
		list-style: none;
		display: flex;
		align-items: center;
	}

	li {
		padding: 0 .5rem;
		display: flex;
		align-items: center;
	}

	a {
		text-decoration: none;
		color: inherit;
	}

	.logo {
		display: flex;
		align-items: center;
	}

	img {
		margin-left: 2rem;
		height: 2rem;
		width: 2rem;
	}

	.navigation {
		align-items: stretch;
		justify-content: center;
	}

	.navigation > li {
		width: 4rem;
		display: flex;
		justify-content: center;
	}

	.navigation > li:hover {
		background: var(--selected-1);
		filter: brightness(125%);
	}

	.navigation > li.selected {
		background: var(--selected-1);
		border-bottom: 2px inset var(--text-1);
	}

	.controls {
		margin-right: 2rem;
		flex-direction: row-reverse;
	}
</style>