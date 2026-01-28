<script>
	import PhotoCarousel from '$lib/components/PhotoCarousel.svelte';
	import { onMount } from 'svelte';

	let innerWidth = $state(0);
	let innerHeight = $state(0);
</script>

<svelte:window bind:innerHeight bind:innerWidth />

<svelte:head>
	<title>Home | Metrobots</title>
</svelte:head>

<main>
	<h1>Welcome to the Metrobots</h1>
	<p>
		The Metrobots is a FIRST Robotics Competition (FRC) team based out of The Past Foundation in
		Columbus, Ohio. Over the years, the team has been Regional Winners, Regional Chairman’s Award
		winners, and Engineering Inspiration Award winners at the regional and world championship
		levels. These awards have allowed The Metrobots to attend the FIRST World Championship 2015,
		2016, 2017 and 2018. We hold outreach events within our community, for instance, we support
		other FIRST (FLL, FTC, FRC) teams, and conduct engineering workshops throughout Ohio.
	</p>
	<PhotoCarousel />
</main>

<style>
	main {
		padding: 2vw 5vw;
	}

	h1 {
		text-align: center;
	}
</style>
