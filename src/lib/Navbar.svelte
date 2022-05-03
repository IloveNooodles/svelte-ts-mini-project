<script lang="ts" context="module">
	import '../styles/global.css';
</script>

<nav>
	<div class="nav-center">
		<h4>Gare's TS Project</h4>
		<ul class="nav-links">
			<li><a href="/">Home</a></li>
			<li><a href="/about">About</a></li>
		</ul>
	</div>
</nav>

<style>
	nav {
		background: var(--clr-white);
		height: 3rem;
		display: grid;
		align-items: center;
		box-shadow: var(--dark-shadow);
	}
	.nav-center {
		width: 90vw;
		max-width: var(--fixed-width);
		margin: 0 auto;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.nav-links {
		display: flex;
	}
	.nav-center h4 {
		margin-bottom: 0;
		color: var(--clr-primary-5);
	}
	nav a {
		text-transform: capitalize;
		font-weight: 700;
		font-size: 1rem;
		color: var(--clr-primary-1);
		letter-spacing: var(--spacing);
		margin-right: 1rem;
	}
	nav a:hover {
		color: var(--clr-primary-5);
	}
</style>
