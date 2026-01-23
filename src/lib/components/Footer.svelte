<script>
	import email_logo from '$lib/assets/icons/email.svg';
	import github_logo from '$lib/assets/icons/logos/github.svg';
</script>

<footer>
	<div id="links-container">
		<a href="mailto:team3324metrobots@gmail.com" target="_blank">
			<img src={email_logo} alt="Metrobots Email" />
			<span class="horizontal-spacer"></span>
			<p>Email: team3324metrobots@gmail.com</p>
		</a>
		<span class="vertical-spacer"></span>
		<a href="https://github.com/metrobots" target="_blank">
			<img src={github_logo} alt="Metrobots Github" />
			<span class="horizontal-spacer"></span>
			<p>Github: metrobots</p>
		</a>
	</div>
</footer>

<style>
	footer {
		background-color: var(--background-color);

		min-height: 15vh;

		padding: 2vh 5vw;
	}

	#links-container {
		display: grid;
		grid-template-rows: auto auto;
	}

	#links-container a {
		height: 100%;

		text-decoration: none;

		display: flex;
		align-items: center;
	}

	#links-container img {
		width: 50px;
		background-color: white;
		border-radius: 10px;
	}

	#links-container p {
		color: white;
	}

	.horizontal-spacer {
		width: 2vw;
	}

	.vertical-spacer {
		height: 4vh;
	}
</style>
