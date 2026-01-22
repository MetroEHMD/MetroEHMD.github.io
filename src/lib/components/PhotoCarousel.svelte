<script>
	import image1 from '$lib/assets/images/temp/1.jpeg';
	import image2 from '$lib/assets/images/temp/2.jpeg';
	import image3 from '$lib/assets/images/temp/3.jpeg';
	import image4 from '$lib/assets/images/temp/4.jpeg';
	import image5 from '$lib/assets/images/temp/5.jpeg';
	import image6 from '$lib/assets/images/temp/6.jpeg';
	import image7 from '$lib/assets/images/temp/7.jpeg';

	const tempImages = [image1, image2, image3, image4, image5, image6, image7];
	let currentImage = $state(0);
	let imageOpacity = $state(1);
	/* The time between image changes in milliseconds. */
	const imageChangeDelay = 5000;
	const fadeDuration = 500;

	function handle_previous() {
		if (currentImage == 0) {
			currentImage = tempImages.length - 1;
		} else {
			currentImage--;
		}
	}

	function handle_next() {
		currentImage = (currentImage + 1) % tempImages.length;
	}

	function change_image() {
		imageOpacity = 0;
		setTimeout(() => {
			// Cycle through images.
			currentImage = (currentImage + 1) % tempImages.length;
			imageOpacity = 1;
		}, fadeDuration);
	}

	setInterval(change_image, imageChangeDelay);
</script>

<div id="carousel">
	<div id="image-container">
		<img src={tempImages[currentImage]} alt="" style="opacity: {imageOpacity};" />
	</div>
	<div id="carousel-controls">
		<!-- Less than symbol -->
		<button type="button" onclick={handle_previous}>&lt;</button>
		<p>{currentImage + 1} / {tempImages.length}</p>
		<!-- Greater than symbol -->
		<button type="button" onclick={handle_next}>&gt;</button>
	</div>
</div>

<style>
	#carousel {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		margin-top: 5vh;
	}

	#image-container {
		aspect-ratio: 1 / 1;
		height: 60vh;
		overflow: hidden;

		margin-bottom: 2.5vh;
	}

	#image-container img {
		object-fit: cover;
		height: 100%;

		transition: opacity 0.5s ease-in-out;
	}

	#carousel-controls {
		display: grid;
		grid-template-columns: auto auto auto;
		column-gap: 30px;
		align-items: center;
	}

	#carousel-controls button {
		aspect-ratio: 1 / 1;
		background: none;
		border: none;
		font-size: 2em;
	}

	#carousel-controls button:hover {
		cursor: pointer;
	}
</style>
