<script lang="ts">
	import { onMount } from 'svelte';
	export let counter: number = 0;
	export let style: string = '#000';
	$: counter = 0;

	onMount(() => {
		const increase = document.querySelector<HTMLButtonElement>('.increase') as HTMLButtonElement;
		const reset = document.querySelector<HTMLButtonElement>('.reset') as HTMLButtonElement;
		const decrease = document.querySelector<HTMLButtonElement>('.decrease') as HTMLButtonElement;
		const value = document.getElementById('value') as HTMLSpanElement;

		if (increase) {
			increase.addEventListener('click', () => {
				counter++;
			});
		}

		if (decrease) {
			decrease.addEventListener('click', () => {
				counter--;
			});
		}

		if (reset) {
			reset.addEventListener('click', () => {
				counter = 0;
			});
		}
	});

	$: {
		if (counter > 0) {
			style = 'green';
		} else if (counter < 0) {
			style = 'red';
		} else {
			style = '#000';
		}
	}
</script>

<main>
	<div class="container">
		<h1>counter</h1>
		<span id="value" style="color: {style}">{counter}</span>
		<div class="button-container">
			<button class="btn decrease">decrease</button>
			<button class="btn reset">reset</button>
			<button class="btn increase">increase</button>
		</div>
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
	#value {
		font-size: 6rem;
		font-weight: bold;
	}
	.btn {
		text-transform: uppercase;
		background: transparent;
		color: var(--clr-black);
		padding: 0.375rem 0.75rem;
		letter-spacing: var(--spacing);
		display: inline-block;
		transition: var(--transition);
		font-size: 0.875rem;
		border: 2px solid var(--clr-black);
		cursor: pointer;
		box-shadow: 0 1px 3px rgba(0, 0, 0, 0.2);
		border-radius: var(--radius);
		margin: 0.5rem;
	}
	.btn:hover {
		color: var(--clr-white);
		background: var(--clr-black);
	}
</style>
