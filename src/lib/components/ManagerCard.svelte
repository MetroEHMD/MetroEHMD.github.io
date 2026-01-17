<script>
	const { data } = $props();
	const { imgUrl, name, role, year } = $derived(data);
</script>

<div class="leader-card">
	<img src={imgUrl} alt="{role} image" class="leader-image" loading="lazy" />
	<div class="leader-content">
		<h2 class="leader-name">{name}</h2>
		<p class="leader-role">{role}</p>
		<p class="leader-description">{year}</p>
	</div>
</div>

<style>
	h2,
	p {
		color: white;
	}

	.leader-card {
		background-color: #333;
		border-radius: 15px;
		overflow: hidden;
		position: relative;
		box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
		transition: transform 0.3s ease-in-out;
	}

	.leader-card:hover {
		transform: scale(1.05);
	}

	.leader-image {
		width: 100%;
		height: 300px;
		object-fit: cover;
	}

	.leader-content {
		padding: 20px;
		background-color: #444;
		color: white;
		text-align: center;
	}

	.leader-name {
		font-size: 1.5rem;
		margin-bottom: 10px;
	}

	.leader-role {
		font-size: 1.2rem;
		margin-bottom: 15px;
		color: #ddd;
	}

	.leader-description {
		font-size: 1rem;
		line-height: 1.5;
	}
</style>
