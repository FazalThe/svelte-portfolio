<script>
	import { fade, fly } from 'svelte/transition';
	import { onMount } from 'svelte';

	// State for animated introduction text
	let visible = false;
	onMount(() => {
		visible = true;
	});

	// Interactive mouse tracking for a subtle parallax effect on the image
	let mouseX = 0;
	let mouseY = 0;

	function handleMouseMove(event) {
		const { clientX, clientY } = event;
		// Normalize values between -1 and 1
		mouseX = (clientX / window.innerWidth) * 2 - 1;
		mouseY = (clientY / window.innerHeight) * 2 - 1;
	}
</script>

<section class="hero-container" on:mousemove={handleMouseMove}>
	<div class="grid-wrapper">
		{#if visible}
			<div class="content-box">
				<div>
					<h1 in:fly={{ y: 30, duration: 800, delay: 400 }}>
						Hey there its 
					</h1>
					<h1 in:fly={{ y: 30, duration: 800, delay: 400 }}>
						<span class="blue-text">Fazal</span> here.
					</h1>
				</div>
				<div class="cta-group" in:fly={{ y: 40, duration: 800, delay: 800 }}>
					<a href="#work" class="btn btn-primary">View My Work</a>
					<a href="#contact" class="btn btn-secondary">Let's Talk</a>
				</div>
			</div>
		{/if}


	</div>
</section>

<style>
	/* Resets & Variables */
	:global(body) {
		margin: 0;
		font-family: 'Inter', system-ui, -apple-system, sans-serif;
		background-color: #3e003c;
		color: #008B8C;
		overflow-x: hidden;
		perspective: 1000px; /* Crucial for the 3D rotation effect */
	}

	.hero-container {
		min-height: 100vh;
		display: flex;
		align-items: center;
		justify-content: center;
		padding: 2rem;
		box-sizing:content-box;
		position: relative;
	}

	.grid-wrapper {
		max-width: 1200px;
		width: 100%;
		display: flex;
		justify-content: center;
	}

	/* Content Styling */
	.content-box {
		max-width: 60%;
		display: flex;
		flex-direction: column;
		justify-items: center;
		gap: 1.5rem;
	}


	h1 {
		color: #ffd900;
		font-family: "Fascinate", system-ui;
		font-size: clamp(2rem, 4vw, 4rem);
		line-height: 1.1;
		font-weight: 700;
		margin: 0;
		letter-spacing: -0.02em;
	}

	.blue-text {
		background-color: #00fddb;
		font-family: "Alien Block", sans-serif;
		font-size: clamp(3.5rem, 7vw, 5.5rem);
  		font-weight: 400;
  		font-style: normal;
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
	}

	.description {
		font-size: clamp(1.1rem, 2vw, 1.3rem);
		line-height: 1.6;
		color: #b3b9c1;
		max-width: 540px;
		margin: 0 0 1rem 0;
	}

	/* Buttons */
	.cta-group {
		display: flex;
		gap: 1rem;
		align-items: center;
	}

	.btn {
		padding: 0.8rem 2rem;
		font-size: 1rem;
		font-weight: 500;
		border-radius: 30px;
		text-decoration: none;
		transition: all 0.3s ease;
	}

	.btn-primary {
		background-color: #ffffff;
		color: #0b0b0f;
	}

	.btn-primary:hover {
		background-color: #e2e2e5;
		transform: translateY(-2px);
	}

	.btn-secondary {
		border: 1px solid rgba(255, 255, 255, 0.15);
		color: #ffffff;
	}

	.btn-secondary:hover {
		background-color: rgba(255, 255, 255, 0.05);
		border-color: rgba(255, 255, 255, 0.3);
	}


</style>
