<script>
	import { Calendar, TimeGrid } from '@event-calendar/core';

	let options = $state({
		view: 'dayGridMonth',
		events: [
			// your list of events
		]
	});
</script>

<main>
	<h1>Calendar</h1>
	<div id="calendar-container">
		<Calendar {options} />
	</div>
</main>

<style>
	main {
		display: flex;
		flex-direction: column;
		align-items: center;
		padding: 50px;
	}

	#calendar-container {
		width: 80vw;
	}
</style>
