<script lang="ts">
	import '../../styles/global.css';
	import { onMount } from 'svelte';

	onMount(() => {
		const btn = document.getElementById('btn') as HTMLElement;
		const color = document.querySelector<HTMLSpanElement>('.color');
		const HEX = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', 'A', 'B', 'C', 'D', 'E', 'F'];
		btn.addEventListener('click', () => {
			let random: string = '#';
			for (let i = 0; i < 6; i++) {
				random += HEX[Math.floor(Math.random() * HEX.length)];
			}

			if (color) {
				color.textContent = random;
				document.body.style.backgroundColor = random;
			}
		});

		if (color) {
			color.addEventListener('click', () => {
				navigator.clipboard.writeText(color.textContent?.toUpperCase() || '').then(() => {
					alert('Copied hex color to the clipboard!');
				});
			});
		}
	});
</script>

<main>
	<div class="container">
		<h2>Background Color: <span class="color"> #f1f5f8 </span></h2>
		<button class="btn btn-hero" id="btn"> click me </button>
	</div>
</main>

<style>
	main {
		min-height: calc(100vh - 3rem);
		display: grid;
		place-items: center;
	}
	.container {
		text-align: center;
	}

	.container h2 {
		background: var(--clr-black);
		color: var(--clr-white);
		padding: 1rem;
		border-radius: var(--radius);
		margin-bottom: 2.5rem;
	}

	.color {
		color: var(--clr-primary-5);
		text-transform: uppercase;
	}
	.btn-hero {
		font-family: var(--ff-primary);
		text-transform: uppercase;
		background: transparent;
		color: var(--clr-black);
		letter-spacing: var(--spacing);
		display: inline-block;
		font-weight: 700;
		transition: var(--transition);
		border: 2px solid var(--clr-black);
		cursor: pointer;
		box-shadow: 0 1px 3px rgba(0, 0, 0, 0.2);
		border-radius: var(--radius);
		font-size: 1rem;
		padding: 0.75rem 1.25rem;
	}
	.btn-hero:hover {
		color: var(--clr-white);
		background: var(--clr-black);
	}
</style>
