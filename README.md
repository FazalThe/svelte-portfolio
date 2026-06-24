# Portfolio

My personal portfolio website built with Svelte and GSAP.

## Why I built this

This was more of a learing project that create a personal website. This is my first svelte project and second ever coded website. I learnt basic svelte and GSAP( also scrolltrigger).

## Built With

* Svelte
* GSAP
* ScrollTrigger
* HTML
* CSS

## Features

* Responsive layout
* Animated landing section
* Scroll-controlled SVG path animation
* Project showcase section
* About section
* Tools and software section

## How It Works

The page starts with a simple intro animation where the text fades in and the SVG path begins drawing itself.

Once the intro animation is complete, the path animation becomes linked to scrolling using GSAP ScrollTrigger. As the user moves through the page, the line continues drawing along its curve.

The SVG drawing effect is created using `strokeDasharray` and `strokeDashoffset`.

## Sections

### Hero

A simple introduction with animated typography.

### About

A short overview about me.

### Tools

A list of software and tools I regularly use.

### Projects

A collection of projects with links to their repositories or live versions.

Current projects include:

* Joy Board
* Grapple Go
* This portfolio

## Development

Clone the repository:

```bash
git clone <https://github.com/FazalThe/svelte-portfolio>
```

Install dependencies:

```bash
npm install
```

Start the development server:

```bash
npm run dev
```

Build for production:

```bash
npm run build
```


