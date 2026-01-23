<script>
	import { resolve } from '$app/paths';
</script>

<main>
	<div id="links-container">
		<h1>Team 3324 Resources</h1>
		<a href={resolve('/resources/swervesim')}>Swerve Simulator</a>
		<a href={resolve('/resources/scouting')}>Scouting App</a>
	</div>
</main>

<style>
	main {
		/* Override */
		min-height: 50vh;

		display: flex;
		flex-direction: column;
		align-items: center;
		padding: 50px;
	}

	#links-container {
		padding: 25px;
		min-height: 50vh;

		background-color: darkgray;
		border: 2px solid darkslategray;
		border-radius: 20px;

		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 20px;
	}

	#links-container a {
		width: 80%;

		padding: 10px;

		text-align: center;

		text-decoration: none;
		background-color: white;
		border: 1px solid black;
		border-radius: 15px;
	}

	#links-container a:hover {
		background-color: lightgray;
	}
</style>
