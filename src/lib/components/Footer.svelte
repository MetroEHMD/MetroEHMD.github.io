<script>
	import email_logo from '$lib/assets/icons/email.svg';
	import github_logo from '$lib/assets/icons/github.svg';
</script>

<footer>
	<div id="links-container">
		<a href="mailto:team3324metrobots@gmail.com">
			<img src={email_logo} alt="Metrobots Email" />
			<span class="horizontal-spacer"></span>
			<p>Email: team3324metrobots@gmail.com</p>
		</a>
		<span class="vertical-spacer"></span>
		<a href="https://github.com/metrobots">
			<img src={github_logo} alt="Metrobots Github" />
			<span class="horizontal-spacer"></span>
			<p>Github: metrobots</p>
		</a>
	</div>
</footer>

<style>
	footer {
		background-color: rgb(100, 155, 255);

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
		width: 5vw;
	}

	.horizontal-spacer {
		width: 2vw;
	}

	.vertical-spacer {
		height: 4vh;
	}
</style>
