<script>
	import { resolve } from '$app/paths';

	// TODO: Move logo to appropriate directory.
	import metrobotsLogo from '$lib/assets/gdb.png';

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
		console.log(`Scroll: ${scroll}`);
	}
</script>

<svelte:window onscroll={handle_scroll} />

<nav class:isCollapsed>
	<a href={resolve('/')}>
		<img id="metrobots-logo" src={metrobotsLogo} alt="Metrobots Logo" />
	</a>
	<div id="page-links">
		<p>About Us</p>
		<p>Our Season</p>
		<p>Our Community</p>
		<p>Resources</p>
	</div>
</nav>

<style>
	nav {
		background-color: lightblue;
		height: 15vh;
		padding: 0 2vw;

		position: sticky;
		top: 0;
		left: 0;
		right: 0;
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

		display: flex;
		align-items: center;
	}

	#metrobots-logo {
		height: 80%;
	}

	#page-links {
		display: flex;
		flex-direction: row;
		justify-content: space-around;

		width: 50%;
	}
</style>
