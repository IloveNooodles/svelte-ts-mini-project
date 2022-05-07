<script lang="ts">
	import '../../styles/fontawesome-free-6.1.1-web/css/all.min.css';
	import '../../styles/global.css';
	import logo from '../../assets/logo.svg';
	export let clicked = false;
</script>

<nav>
	<div class="nav-center">
		<!-- nav header  -->
		<div class="nav-header">
			<img src={logo} alt="" class="logo" />
			<button
				class="nav-toggle"
				on:click={() => {
					clicked = !clicked;
				}}
			>
				<i class="fas fa-bars" />
			</button>
		</div>
		<!-- end of header -->
		<ul class="links" class:show-links={clicked}>
			<li>
				<a href="/">home</a>
			</li>
			<li>
				<a href="/about">about</a>
			</li>
			<li>
				<a href="/">projects</a>
			</li>
			<li>
				<a href="https://www.linkedin.com/in/garebaldhie">contact</a>
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
	</div>
</nav>

<style>
	nav {
		background: var(--clr-white);
		box-shadow: var(--light-shadow);
	}
	.nav-header {
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 1rem;
	}
	.nav-toggle {
		font-size: 1.5rem;
		color: var(--clr-primary-5);
		background: transparent;
		border-color: transparent;
		transition: var(--transition);
		cursor: pointer;
	}
	.nav-toggle:hover {
		color: var(--clr-primary-1);
		transform: rotate(90deg);
	}
	.logo {
		height: 40px;
	}
	.links a {
		color: var(--clr-grey-3);
		font-size: 1rem;
		text-transform: capitalize;
		letter-spacing: var(--spacing);
		display: block;
		padding: 0.5rem 1rem;
	}

	.links {
		height: 0;
		overflow: hidden;
		transition: var(--transition);
	}

	.links a:hover {
		background: var(--clr-primary-8);
		color: var(--clr-primary-5);
		padding-left: 1.5rem;
	}

	.social-icons {
		display: none;
	}

	.show-links {
		height: 10rem;
	}

	@media screen and (min-width: 800px) {
		.nav-center {
			max-width: 1170px;
			margin: 0 auto;
			display: flex;
			align-items: center;
			justify-content: space-between;
			padding: 1rem;
		}
		.nav-header {
			padding: 0;
		}
		.nav-toggle {
			display: none;
		}
		.links {
			height: auto;
			display: flex;
		}
		.links a {
			padding: 0;
			margin: 0 0.5rem;
		}
		.links a:hover {
			padding: 0;
			background: transparent;
		}
		.social-icons {
			display: flex;
		}
		.social-icons a {
			margin: 0 0.5rem;
			color: var(--clr-primary-5);
			transform: var(--transition);
		}
		.social-icons a:hover {
			color: var(--clr-primary-7);
		}
	}
</style>
