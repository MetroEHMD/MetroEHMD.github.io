<script>
	import image1 from '$lib/assets/images/temp/1.jpeg';
	import image2 from '$lib/assets/images/temp/2.jpeg';
	import image3 from '$lib/assets/images/temp/3.jpeg';
	import image4 from '$lib/assets/images/temp/4.jpeg';
	import image5 from '$lib/assets/images/temp/5.jpeg';
	import image6 from '$lib/assets/images/temp/6.jpeg';
	import image7 from '$lib/assets/images/temp/7.jpeg';

	const tempImages = [image1, image2, image3, image4, image5, image6, image7];
	let current_image = $state(0);
	let imageOpacity = $state(1);
	/* The time between image changes in milliseconds. */
	const imageChangeDelay = 5000;
	const fadeDuration = 500;

	function change_image() {
		imageOpacity = 0;
		setTimeout(() => {
			// Cycle through images.
			current_image = (current_image + 1) % tempImages.length;
			imageOpacity = 1;
		}, fadeDuration);
	}

	setInterval(change_image, imageChangeDelay);
</script>

<div id="carousel">
	<div id="image-container">
		<img src={tempImages[current_image]} alt="" style="opacity: {imageOpacity};" />
	</div>
</div>

<style>
	#carousel {
		display: flex;
		justify-content: center;
		align-items: center;
		margin-top: 5vh;
	}

	#image-container {
		aspect-ratio: 1 / 1;
		height: 60vh;
		overflow: hidden;
	}

	#image-container img {
		object-fit: cover;
		height: 100%;

		transition: opacity 0.5s ease-in-out;
	}

	/* #image-container img:hover {
		opacity: 0;

		cursor: pointer;
	} */
</style>
