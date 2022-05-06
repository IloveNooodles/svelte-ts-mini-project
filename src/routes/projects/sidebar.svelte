<script lang="ts">
	import '../../assets/fontawesome-free-6.1.1-web/css/all.min.css';
	import '../../styles/global.css';
	import logo from '../../assets/logo.svg';
	export let showSidebar: boolean = false;
</script>

<main>
	<button
		class="sidebar-toggle"
		on:click={() => {
			showSidebar = true;
		}}
	>
		<i class="fas fa-bars" />
	</button>
	<aside class="sidebar" class:show-sidebar={showSidebar}>
		<div class="sidebar-header">
			<img class="logo" src={logo} alt="" />
			<button
				class="close-btn"
				on:click={() => {
					showSidebar = false;
				}}
			>
				<i class="fas fa-times" />
			</button>
		</div>
		<!-- links -->
		<ul class="links">
			<li>
				<a href="index.html">home</a>
			</li>
			<li>
				<a href="about.html">about</a>
			</li>
			<li>
				<a href="projects.html">projects</a>
			</li>
			<li>
				<a href="contact.html">contact</a>
			</li>
		</ul>
		<!-- social media -->
		<ul class="social-icons">
			<li>
				<a href="https://www.twitter.com">
					<i class="fab fa-facebook" />
				</a>
			</li>
			<li>
				<a href="https://www.twitter.com">
					<i class="fab fa-twitter" />
				</a>
			</li>
			<li>
				<a href="https://www.twitter.com">
					<i class="fab fa-behance" />
				</a>
			</li>
			<li>
				<a href="https://www.twitter.com">
					<i class="fab fa-linkedin" />
				</a>
			</li>
			<li>
				<a href="https://www.twitter.com">
					<i class="fab fa-sketch" />
				</a>
			</li>
		</ul>
		<!-- end of links  -->
	</aside>
</main>

<style>
	.sidebar-toggle {
		position: fixed;
		top: 2rem;
		right: 3rem;
		font-size: 2rem;
		background: transparent;
		border-color: transparent;
		color: var(--clr-primary-5);
		transition: var(--transition);
		cursor: pointer;
		animation: bounce 2s ease-in-out infinite;
	}
	.sidebar-toggle:hover {
		color: var(--clr-primary-7);
	}
	@keyframes bounce {
		0% {
			transform: scale(1);
		}
		50% {
			transform: scale(1.5);
		}
		100% {
			transform: scale(1);
		}
	}

	.sidebar-header {
		display: flex;
		justify-content: space-between;
		align-items: center;
		padding: 1rem 1.5rem;
	}
	.close-btn {
		font-size: 1.75rem;
		background: transparent;
		border-color: transparent;
		color: var(--clr-primary-5);
		transition: var(--transition);
		cursor: pointer;
		color: var(--clr-red-dark);
	}
	.close-btn:hover {
		color: var(--clr-red-light);
		transform: rotate(360deg);
	}
	.logo {
		justify-self: center;
		height: 40px;
	}

	.links a {
		display: block;
		font-size: 1.5rem;
		text-transform: capitalize;
		padding: 1rem 1.5rem;
		color: var(--clr-grey-5);
		transition: var(--transition);
	}
	.links a:hover {
		background: var(--clr-primary-8);
		color: var(--clr-primary-5);
		padding-left: 1.75rem;
	}
	.social-icons {
		justify-self: center;
		display: flex;
		padding-bottom: 2rem;
	}
	.social-icons a {
		font-size: 1.5rem;
		margin: 0 0.5rem;
		color: var(--clr-primary-5);
		transition: var(--transition);
	}
	.social-icons a:hover {
		color: var(--clr-primary-1);
	}

	.sidebar {
		position: fixed;
		top: 0;
		left: 0;
		width: 100%;
		height: 100%;
		background: var(--clr-white);
		display: grid;
		grid-template-rows: auto 1fr auto;
		row-gap: 1rem;
		box-shadow: var(--clr-red-dark);
		transition: var(--transition);
		transform: translate(-100%);
	}
	.show-sidebar {
		transform: translate(0);
	}
	@media screen and (min-width: 676px) {
		.sidebar {
			width: 400px;
		}
	}
</style>
