<script>
	import image1 from '$lib/assets/images/gallery/1.jpg';
	import image2 from '$lib/assets/images/gallery/2.jpg';
	import image3 from '$lib/assets/images/gallery/3.jpg';
	import image4 from '$lib/assets/images/gallery/4.jpg';
	import image5 from '$lib/assets/images/gallery/5.jpg';
	import image6 from '$lib/assets/images/gallery/6.jpg';
	import image7 from '$lib/assets/images/gallery/7.jpg';
	import image8 from '$lib/assets/images/gallery/8.png';
	import image9 from '$lib/assets/images/gallery/9.png';
	import image10 from '$lib/assets/images/gallery/10.jpg';
	import image11 from '$lib/assets/images/gallery/11.jpg';
	import image12 from '$lib/assets/images/gallery/12.jpg';
	import image13 from '$lib/assets/images/gallery/13.jpg';
	import image14 from '$lib/assets/images/gallery/14.jpg';
	import image15 from '$lib/assets/images/gallery/15.jpg';
	import image16 from '$lib/assets/images/gallery/16.jpg';
	import image17 from '$lib/assets/images/gallery/17.jpg';
	import image18 from '$lib/assets/images/gallery/18.jpg';
	import image19 from '$lib/assets/images/gallery/19.jpg';
	import image20 from '$lib/assets/images/gallery/20.jpg';
	import image21 from '$lib/assets/images/gallery/21.jpg';
	import image22 from '$lib/assets/images/gallery/22.jpg';
	import image23 from '$lib/assets/images/gallery/23.jpg';
	import image24 from '$lib/assets/images/gallery/24.jpg';
	import image25 from '$lib/assets/images/gallery/25.jpg';
	import image26 from '$lib/assets/images/gallery/26.jpg';
	import image27 from '$lib/assets/images/gallery/27.jpg';
	import image28 from '$lib/assets/images/gallery/28.jpg';
	import image29 from '$lib/assets/images/gallery/29.png';

	const photos = [
		image1,
		image2,
		image3,
		image4,
		image5,
		image6,
		image7,
		image8,
		image9,
		image10,
		image11,
		image12,
		image13,
		image14,
		image15,
		image16,
		image17,
		image18,
		image19,
		image20,
		image21,
		image22,
		image23,
		image24,
		image25,
		image26,
		image27,
		image28,
		image29
	];
</script>

<svelte:head>
	<title>Gallery | Metrobots</title>
</svelte:head>

<main>
	<div id="gallery-photos-container">
		{#each photos as photo, index}
			<div class="gallery-item">
				<img src={photo} alt="Image {index + 1}" loading="lazy" />
				<div class="image-label">Image {index + 1}</div>
			</div>
		{/each}
	</div>
</main>

<style>
	#gallery-photos-container {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
		gap: 20px;
		grid-auto-rows: 250px;
		padding: 50px;
	}

	.gallery-item {
		background-color: #333;
		border-radius: 10px;
		overflow: hidden;
		position: relative;
		cursor: pointer;
		animation: slideIn 1s ease-out both;
	}

	.gallery-item:hover {
		transform: scale(1.05);
	}

	.gallery-item img {
		width: 100%;
		height: 100%;
		object-fit: cover;
		opacity: 0.8;
		transition: opacity 0.3s ease-in-out;
	}
</style>
