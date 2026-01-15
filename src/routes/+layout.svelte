<script>
	import metrobotsAppleTouchIcon from '$lib/assets/favicon/apple-touch-icon.png';
	import metrobots32x32Logo from '$lib/assets/favicon/favicon-32x32.png';
	import metrobots16x16Logo from '$lib/assets/favicon/favicon-16x16.png';
	import Navbar from '$lib/components/Navbar.svelte';
	import Footer from '$lib/components/Footer.svelte';
	import '../app.css';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="apple-touch-icon" sizes="180x180" href={metrobotsAppleTouchIcon} />
	<link rel="icon" type="image/png" sizes="32x32" href={metrobots32x32Logo} />
	<link rel="icon" type="image/png" sizes="16x16" href={metrobots16x16Logo} />
</svelte:head>

<Navbar />

<!-- Render the current page. -->
{@render children()}

<Footer />
