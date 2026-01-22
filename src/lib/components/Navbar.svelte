<script>
	import { resolve } from '$app/paths';
	import hamburgerIcon from '$lib/assets/icons/hamburger_menu.svg';
	import metrobotsLogo from '$lib/assets/favicon/fancy-metrobots-logo.png';

	// Used on on desktop to collapse navbar on scroll.
	let isCollapsed = $state(false);
	// Use for mobile navigation
	let isHidden = $state(true);

	function handle_scroll() {
		isCollapsed = window.scrollY > 0;
	}

	function handle_hamburger() {
		isHidden = !isHidden;
	}
</script>

<svelte:window onscroll={handle_scroll} />

<nav class:isCollapsed class:isHidden>
	<a href={resolve('/')}>
		<img id="metrobots-logo" src={metrobotsLogo} alt="Metrobots Logo" />
	</a>
	<button onclick={handle_hamburger} id="hamburger-button">
		<img src={hamburgerIcon} alt="" />
	</button>
	<div id="page-links" class:isHidden>
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

	#hamburger-button {
		background: none;
		border: none;
		aspect-ratio: 1 / 1;

		cursor: pointer;

		display: none;
	}

	/* TODO: Change this to a less arbitrary value. */
	@media (width <= 900px) {
		#hamburger-button {
			display: inline-block;
		}

		#page-links.isHidden {
			display: none;
		}

		#page-links:not(.isHidden) {
			animation-name: slide-from-top;
			animation-duration: 1s;

			position: fixed;
			top: 19vh;
			left: 0;
			right: 0;
			width: 100%;
			padding: 20px;

			display: flex;
			flex-direction: column;
			align-items: center;

			background-color: var(--secondary-background-color);
		}

		nav.isCollapsed #page-links:not(.isHidden) {
			top: 12vh;
		}

		@keyframes slide-from-top {
			from {
				translate: 0 -50vh;
			}

			to {
				translate: 0;
			}
		}
	}
</style>
