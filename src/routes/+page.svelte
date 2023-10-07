<script>
	import Spline from "./Spline.svelte";
	let loading = true;
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte & Spline demo app" />
</svelte:head>

<section class="hero">
	<div class="parent">
		<div class="content-left">
			<h1>FUTURE IS HERE</h1>
			<p>
				Lorem ipsum dolor sit amet consectetur, adipisicing elit. Soluta
				inventore dolore nesciunt unde laudantium alias sit, quia quasi
				voluptas nulla culpa sunt quaerat accusantium esse libero
				beatae, in minima aperiam.
			</p>
			<button> S P L I N E </button>
		</div>
		<div class="content-right">Content</div>
	</div>

	<Spline
		setLoading={() => {
			loading = false;
		}}
	/>
</section>

<style>
	h1,
	p {
		font-family: sans-serif;
	}
	h1 {
		font-size: 36px;
		font-weight: bold;
		color: #fdfdfd;
	}
	p {
		font-size: 16px;
		color: #e29531;
		width: 80%;
		display: block;
	}

	.hero {
		height: calc(100vh);
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: flex-start;
		position: relative;
		gap: 1em;
		padding-top: min(10%, 256px);
		margin: auto;
	}

	.parent {
		display: grid;
		grid-template-columns: 2fr 1fr;
		grid-column-gap: 0px;
		grid-row-gap: 0px;
		opacity: 0;
		animation: fadeIn 0.7s cubic-bezier(1, 0, 1, 0);
		animation-fill-mode: forwards;
		animation-delay: 7.2s;
		animation-iteration-count: 1;
	}

	.content-left {
		padding: 1em;
		display: flex;
		align-items: flex-start;
		justify-content: flex-start;
		flex-direction: column;
		gap: 3em;
		max-width: 80%;
		margin: auto;
	}

	button {
		max-width: 256px;
		width: 100%;
		text-align: center;
		color: #fff;
		font-family: sans-serif;
		background-color: #e29531;
		padding: 1em;
		border: 2px solid #fff;
		outline: none;
		transition: 300ms all;
	}

	button:hover {
		transform: scale(1.02);
		box-shadow: 0px 6px 1px 0px rgba(0, 0, 0, 0.1);
	}

	@keyframes fadeIn {
		from {
			opacity: 0;
		}

		to {
			opacity: 1;
		}
	}
</style>
