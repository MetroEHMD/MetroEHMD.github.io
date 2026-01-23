<script>
	import { page } from '$app/state';
</script>

<svelte:head>
	<title>Error Page | Metrobots</title>
</svelte:head>

<main>
	<h1>Error: {page.error.message}</h1>
	<p>Page Not Found</p>
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	main > * {
		font-size: 3em;
	}
</style>
