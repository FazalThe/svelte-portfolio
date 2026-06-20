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
					<h1 in:fly={{ y: 30, duration: 800, delay: 400 }}>
						Hey there its 
					</h1>
					<h1 in:fly={{ y: 30, duration: 800, delay: 400 }}>
						<span class="blue-text">Fazal</span> here.
					</h1>

			</div>

		{/if}

	</div>
</section>

<svg class="curvy-overlay" viewBox="0 0 200 400" preserveAspectRatio="xMidYMid meet">
	<path class="stroke" d="M 50 0 C 00 60, 160 120, 90 200 C 30 260, 150 320, 100 400" 
		fill="none" opacity="l" stroke-linecap="round"/>
</svg>





<style>
	/* Resets & Variables */
	:global(body) {
		margin: 0;
		font-family: 'Inter', system-ui, -apple-system, sans-serif;
		background-color: #FFDD00;
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
		height: 100%;
		display: flex;
		justify-content: center;
	}

	/* Content Styling */
	.content-box {
		max-width: 70%;
		display: flex;
		flex-direction: column;
		justify-items: center;
		gap: 1.5rem;
	}


	h1 {
		color: #00cfb4;
		font-family: "Fascinate", system-ui;
		font-size: clamp(2rem, 4vw, 5.5rem);
		line-height: 1.1;
		font-weight: 700;
		margin: 0;
		letter-spacing: -0.02em;
	}

	.blue-text {
		background-color: #00cfb4;
		font-family: "Alien Block", sans-serif;
		font-size: clamp(3.5rem, 7vw, 7rem);
  		font-weight: 400;
  		font-style: normal;
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
	}

	/* Buttons */
	.cta-group {
		display: flex;
		gap: 1rem;
		align-items: center;
		justify-content: center;
	}

	.btn {
		padding: 0.8rem 2rem;
		font-size: 1rem;
		font-weight: 500;
		border-radius: 30px;
		text-decoration: none;
		transition: all 0.3s ease;
	}

	
	
	.curvy-overlay {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		pointer-events: none;
		z-index: 9999;
		mix-blend-mode: exclusion;
	}

	.stroke {
		stroke: #FFDD00;
		stroke-width: 40;
	}


</style>
