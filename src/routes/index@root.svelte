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
    justify-content: center;
    align-self: center;
    align-items: center;
  }

  .home h1 {
    margin-top: 2rem;
  }

  .links-container {
    height: 70vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 4rem;
    font-size: 2rem;
    flex-wrap: wrap;
    margin-top: 3rem;
    flex-grow: 1;
    align-content: center;
    align-self: center;
  }

  .links-container a {
    margin: 0 5rem;
    transition: 0.3s ease-in-out;
  }

  .links-container a:hover {
    color: red;
  }
</style>
