<script>
	import { resolve } from '$app/paths';

	// TODO: Move logo to appropriate directory.
	import metrobotsLogo from '$lib/assets/favicon/fancy-metrobots-logo.png';

	let isCollapsed = $state(false);

	function handle_scroll(event) {
		let scroll = window.scrollY;
		const scrollThreshold = 50;
		/* It's necessary to have a margin of error, since changing the size of
        the navbar changes the scroll of he window. */
		const margin = 30;
		isCollapsed = scroll > scrollThreshold;
		if (!isCollapsed && scroll > scrollThreshold + margin) {
			isCollapsed = true;
		} else if (isCollapsed && scroll < scrollThreshold - margin) {
			isCollapsed = false;
		}
	}
</script>

<svelte:window onscroll={handle_scroll} />

<nav class:isCollapsed>
	<a href={resolve('/')}>
		<img id="metrobots-logo" src={metrobotsLogo} alt="Metrobots Logo" />
	</a>
	<div id="page-links">
		<a href={resolve('/leadership')}>Leadership</a>
		<a href={resolve('/season')}>2025-2026 Season</a>
		<a href={resolve('/resources')}>Resources</a>
		<a href={resolve('/gallery')}>Gallery</a>
	</div>
</nav>

<style>
	nav {
		background-color: var(--background-color);
		height: 15vh;
		padding: 2vh 2vw;

		position: sticky;
		top: 0;
		left: 0;
		right: 0;
		z-index: 2;
		transition: height 0.5s ease;

		display: flex;
		flex-direction: row;
		justify-content: space-between;
		align-items: center;
	}

	nav.isCollapsed {
		height: 8vh;
	}

	nav a {
		height: 100%;

		text-decoration: none;

		display: flex;
		align-items: center;

		color: var(--on-background-color);
	}

	#metrobots-logo {
		height: 80%;
		background-color: white;
		border-radius: 30px;
	}

	#page-links {
		display: flex;
		flex-direction: row;
		justify-content: space-around;

		width: 50%;
	}
</style>
