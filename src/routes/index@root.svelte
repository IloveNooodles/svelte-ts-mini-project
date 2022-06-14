<script lang="ts">
	import { onMount } from 'svelte/internal';
	onMount(() => {
		document.body.style.backgroundColor = '#F1F5F8';
	});
</script>

<div class="home">
	<h1>Welcome to gare's svelte + ts project</h1>
	<!-- cards container  -->
	<div class="links-container">
		<a href="/projects/countdown">countdown</a>
		<a href="/projects/counter">counter</a>
		<a href="/projects/hex">hex</a>
		<a href="/projects/loremipsum">loremipsum</a>
		<a href="/projects/menu">menu</a>
		<a href="/projects/modals">modals</a>
		<a href="/projects/navbar">navbar</a>
		<a href="/projects/questions">questions</a>
		<a href="/projects/review">review</a>
		<a href="/projects/sidebar">sidebar</a>
		<a href="/projects/video">video</a>
	</div>
</div>

<style>
	.home {
    text-align: center;
	}

	.home h1 {
		margin-top: 2rem;
	}

	.links-container {
    margin-top: 2rem;
    margin-bottom: 2rem;
		display: grid;
    gap: 1rem;
  }

	.links-container a {
		margin: 0 5rem;
		transition: 0.3s ease-in-out;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    font-size: 1.5rem;
	}

	.links-container a:hover {
		color: red;
	}

  @media only screen and (min-width: 768px) {
    .links-container {
      grid-template-columns: 1fr 1fr;
    }
  }

  @media only screen and (min-width: 1024px){
    .links-container {
      grid-template-columns: 1fr 1fr 1fr;
    }
  }
</style>
