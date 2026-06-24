<script>
	import { onMount } from 'svelte';
	import { gsap } from 'gsap';
	import { ScrollTrigger } from 'gsap/ScrollTrigger';
	
	gsap.registerPlugin(ScrollTrigger);


	onMount(() => {
		const tl = gsap.timeline({ defaults: { ease: 'power3.out' } });

		tl.from('.content-box h1', { y: 30, opacity: 0, duration: 0.8, stagger: 0.2 })
		.fromTo(
			'.stroke',
			{
				strokeDasharray: 600,
				strokeDashoffset: 600
			},
			{
				strokeDashoffset: 450,
				duration: 1,
				ease: 'power2.inOut',
				onComplete() {
					gsap.to('.stroke', {
						strokeDashoffset: 0,
						ease: 'none',
						scrollTrigger: {
							trigger: '#about',
							start: 'top center',
							end: 'bottom top',
							scrub: 1,
							snap: {
								snapTo: [0, 0.33, 0.66, 1],
							}
						}
					});
				}
			}
		);
	});
</script>


<section class="hero-container">

	
	<div class="content-box">
		<h1>
			Hey there, its
		</h1>
		<h1>
			<span class="blue-text">Fazal</span> here.
		</h1>
	</div>
	
</section>

<svg class="curvy-overlay" viewBox="0 0 200 400" preserveAspectRatio="xMidYMin">
	<path class="stroke" d="M 50 -10 C 00 60, 160 120, 90 200 C 30 260, 150 320, 100 400 C 30 480, 100 550, 90 630" 
		fill="none" opacity="1" stroke-linecap="round"/>
</svg>


<div class="me">
	<section id="about">
		<h2>About Me</h2>
		<p>An 18yo from Kerala, India. I love learning new stuff, or you could say that I have shiny object syndrome.</p>
	</section>

	<section id="tools">
		<h2>Tools I Use</h2>
		<ul>
			<li>KiCAD</li>
			<li>Fusion 360</li>
			<li>Godot</li>
			<li>Figma</li>
			<li>Svelte</li>
			<li>DaVinci Resolve</li>
		</ul>
	</section>
</div>

<section id="projects">
	<h2>Projects</h2>
	<div>
		<article>
		<a href="https://github.com/FazalThe/Joy-Board" target="_blank">
			<h3>Joy Board</h3>
			<img src="/Render.png" width="100%" alt="Joy Board">
			<p>Custom Ergonomic Split Kyeboard, with a thumb joystick on the left side which can mimmick keypresses when moved to each direction.</p>
		</a>
		</article>
		<article>
		<a href="https://fazalthe.itch.io/grapple-go" target="_blank">
			<h3>Grapple Go</h3> 
			<img src="/Grapple.png" alt="grapple go" width="100%">
			<p>A grappling platformer.</p>
		</a>
		</article>
		<article>
			<h3>Svelte Portfolio</h3>
			<p>This itself ;)</p>
		</article>
	</div>
</section>





<style>
	:global(body) {
		margin: 0;
		font-family: 'Inter', system-ui, -apple-system, sans-serif;
		background-color: #FFDD00;
		color: #008B8C;
		overflow-x: hidden;
		perspective: 1000px; 
	}

	img {
		border-radius: 20px;
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

	/* Content Styling */
	.content-box {
		max-width: 100%;
		display: flex;
		flex-direction: column;
		justify-items: center;
		gap: 1.5rem;
	}


	h1 {
		color: #009985;
		font-family: "Fascinate", system-ui;
		font-size: clamp(2rem, 4vw, 7rem);
		line-height: 1.1;
		font-weight: 700;
		margin: 0;
		letter-spacing: -0.02em;
	}

	.blue-text {
		background-color: #f87687;
		font-family: "Alien Block", sans-serif;
		font-size: clamp(3.5rem, 8vw, 12rem);
  		font-weight: 400;
  		font-style: normal;
		background-clip: text;
		-webkit-background-clip: text;
		-webkit-text-fill-color: transparent;
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
		stroke-width: 35;
	}

	.me {
		display: flex;
		width: 100%;
		flex-direction: row;
		flex-wrap: wrap;
		justify-content: center;
		gap: 5%;
		margin: 0px;
		padding: 0px;
		
	}

	#about {
		background-color: #009985;
		border-radius: 15px;
		padding: 30px;
		width: 40%;


	}

	#about h2{
		color: #FFDD00;
	}

	section{
		margin: 10px;
		margin-bottom: 150px;
		min-width: 400px;
	}

	section h2 {
		font-family: "Fascinate", system-ui;
		font-size: clamp(2rem, 5vw, 3.5rem);
		color: #ec7f89;
		margin: 0 0 2rem;
	}

	#about p {
		font-size: 1.2rem;
		line-height: 1.6;
		max-width: 600px;
		color: #FFDD00;
	}

	#tools ul {
		list-style: none;
		padding: 0;
		display: flex;
		flex-wrap: wrap;
		justify-content: center;
		gap: 1rem;
	}

	#tools {
		width: 40%;
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
		width: 100%;
	}

	#projects article {
		background: #009985;
		color: #FFDD00;
		width: 30%;
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

	#projects div {
		margin-top: 30px;
		display: flex;
		flex-direction: row;
		width: 100%;
		gap: 10%;
		flex-wrap: wrap;
		justify-content: center ;
	}

	a {
		
		text-decoration: none;
		color: inherit;
	}
</style>
