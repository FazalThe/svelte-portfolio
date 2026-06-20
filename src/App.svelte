<script>
	import { onMount } from 'svelte';
	import { gsap } from 'gsap';

	onMount(() => {
		const tl = gsap.timeline({ defaults: { ease: 'power3.out' } });

		tl.from('.content-box h1', { y: 30, opacity: 0, duration: 0.8, stagger: 0.2 })
			.fromTo('.stroke',
				{ strokeDasharray: 600, strokeDashoffset: 600 },
				{ strokeDashoffset: 0, duration: 2, ease: 'power2.inOut' },
			'-=0.5');
	});
</script>


<section class="hero-container">

	<div class="grid-wrapper">
		<div class="content-box">
			<h1>
				Hey there its
			</h1>
			<h1>
				<span class="blue-text">Fazal</span> here.
			</h1>
		</div>
	</div>
</section>

<svg class="curvy-overlay" viewBox="0 0 200 400" preserveAspectRatio="xMidYMid meet">
	<path class="stroke" d="M 50 -10 C 00 60, 160 120, 90 200 C 30 260, 150 320, 100 400" 
		fill="none" opacity="1" stroke-linecap="round"/>
</svg>

<section id="about">
	<h2>About Me</h2>
	<p>A brief intro about who you are, what you do, and what you're passionate about.</p>
</section>

<section id="tools">
	<h2>Tools I Use</h2>
	<ul>
		<li>Tool 1</li>
		<li>Tool 2</li>
		<li>Tool 3</li>
		<li>Tool 4</li>
	</ul>
</section>

<section id="projects">
	<h2>Projects</h2>
	<article>
		<h3>Project Name</h3>
		<p>Short description of the project.</p>
	</article>
	<article>
		<h3>Project Name</h3>
		<p>Short description of the project.</p>
	</article>
	<article>
		<h3>Project Name</h3>
		<p>Short description of the project.</p>
	</article>
</section>





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
		color: #009985;
		font-family: "Fascinate", system-ui;
		font-size: clamp(2rem, 4vw, 5.5rem);
		line-height: 1.1;
		font-weight: 700;
		margin: 0;
		letter-spacing: -0.02em;
	}

	.blue-text {
		background-color: #f87687;
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
		mix-blend-mode:exclusion;
	}

	.stroke {
		stroke: #FFDD00;
		stroke-width: 40;
	}

	section {
		padding: 4rem 2rem;
		max-width: 1000px;
		margin: 0 auto;
	}

	section h2 {
		font-family: "Fascinate", system-ui;
		font-size: clamp(2rem, 5vw, 3.5rem);
		color: #008b8c;
		margin: 0 0 2rem;
	}

	#about p {
		font-size: 1.2rem;
		line-height: 1.6;
		max-width: 600px;
		color: #006b6c;
	}

	#tools ul {
		list-style: none;
		padding: 0;
		display: flex;
		flex-wrap: wrap;
		gap: 1rem;
	}

	#tools li {
		background: #008b8c;
		color: #FFDD00;
		padding: 0.6rem 1.4rem;
		border-radius: 999px;
		font-weight: 600;
		font-size: 0.95rem;
	}

	#projects {
		display: flex;
		flex-direction: column;
	}

	#projects article {
		background: #00b8a0;
		color: #FFDD00;
		padding: 2rem;
		border-radius: 1rem;
		margin-bottom: 1.5rem;
	}

	#projects h3 {
		font-family: "Fascinate", system-ui;
		font-size: 1.5rem;
		margin: 0 0 0.5rem;
	}

	#projects p {
		margin: 0;
		line-height: 1.5;
	}
</style>
