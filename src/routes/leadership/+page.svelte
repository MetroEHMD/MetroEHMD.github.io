<script>
	import mechanical1 from '$lib/assets/images/management/mechanical1.png';
	import mechanical2 from '$lib/assets/images/management/mechanical2.png';
	import mechanical3 from '$lib/assets/images/management/mechanical3.png';
	import electrical1 from '$lib/assets/images/management/electrical1.jpg';
	import programming1 from '$lib/assets/images/management/programming1.png';
	import epm from '$lib/assets/images/management/epm.jpg';
	import bam1 from '$lib/assets/images/management/bam1.jpg';
	import ManagerCard from '$lib/components/ManagerCard.svelte';

	const managers = [
		{
			imgUrl: epm,
			name: 'Mateo Johnson',
			role: 'Engineering Project Manager',
			year: 'Senior'
		},
		{
			imgUrl: bam1,
			name: 'Sophie Tran',
			role: 'Administrative Project Manager',
			year: 'Senior'
		},
		{
			imgUrl: programming1,
			name: 'Evergreen Spanos',
			role: 'Programming Manager',
			year: 'Senior'
		},
		{
			imgUrl: mechanical1,
			name: 'Elijah',
			role: 'Mechanical Manager',
			year: 'Senior'
		},
		{
			imgUrl: mechanical2,
			name: 'Isha Joshi',
			role: 'Mechanical Manager',
			year: 'Junior'
		},
		{
			imgUrl: mechanical3,
			name: 'Fozia Eidarus',
			role: 'Mechanical Manager',
			year: 'Junior'
		},
		{
			imgUrl: electrical1,
			name: 'Zamir Latta',
			role: 'Electrical Manager',
			year: 'Senior'
		}
	];
</script>

<svelte:head>
	<title>Leadership</title>
</svelte:head>

<main>
	<div id="managers-container">
		{#each managers as manager}
			<ManagerCard data={manager} />
		{/each}
	</div>
</main>

<style>
	#managers-container {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
		gap: 20px;

		padding: 100px 150px;
	}
</style>
