<script lang="ts">
	import '../../styles/fontawesome-free-6.1.1-web/css/all.min.css';
	import '../../styles/global.css';
	import { onMount } from 'svelte/internal';

	onMount(() => {
		const btns = document.querySelectorAll('.question-btn')!;
		btns.forEach(function (btn) {
			btn.addEventListener('click', function (e) {
				const question = e.currentTarget as Element;
				question.parentElement?.parentElement?.classList.toggle('show-text');
			});
		});
	});
</script>

<body>
	<section class="questions">
		<!-- title  -->
		<div class="title">
			<h2>general questions</h2>
		</div>
		<!-- questions  -->
		<div class="section-center">
			<!-- single question  -->
			<article class="question show-text">
				<div class="question-title">
					<p>do you accept all major credit cards?</p>
					<button type="button" class="question-btn">
						<span class="plus-icon">
							<i class="far fa-plus-square" />
						</span>
						<span class="minus-icon">
							<i class="far fa-minus-square" />
						</span>
					</button>
				</div>
				<!-- question text  -->
				<div class="question-text">
					<p>
						Lorem ipsum dolor sit amet consectetur adipisicing elit. Mollitia quod nobis minus
						quaerat fugit maxime veritatis temporibus magni recusandae iusto.
					</p>
				</div>
			</article>
			<!-- end of single question  -->
			<!-- single question  -->
			<article class="question">
				<div class="question-title">
					<p>do you accept all major credit cards?</p>
					<button type="button" class="question-btn">
						<span class="plus-icon">
							<i class="far fa-plus-square" />
						</span>
						<span class="minus-icon">
							<i class="far fa-minus-square" />
						</span>
					</button>
				</div>
				<!-- question text  -->
				<div class="question-text">
					<p>
						Lorem ipsum dolor sit amet consectetur adipisicing elit. Mollitia quod nobis minus
						quaerat fugit maxime veritatis temporibus magni recusandae iusto.
					</p>
				</div>
			</article>
			<!-- end of single question  -->
			<!-- single question  -->
			<article class="question">
				<div class="question-title">
					<p>do you accept all major credit cards?</p>
					<button type="button" class="question-btn">
						<span class="plus-icon">
							<i class="far fa-plus-square" />
						</span>
						<span class="minus-icon">
							<i class="far fa-minus-square" />
						</span>
					</button>
				</div>
				<!-- question text  -->
				<div class="question-text">
					<p>
						Lorem ipsum dolor sit amet consectetur adipisicing elit. Mollitia quod nobis minus
						quaerat fugit maxime veritatis temporibus magni recusandae iusto.
					</p>
				</div>
			</article>
			<!-- end of single question  -->
		</div>
	</section>
</body>

<style>
	.title {
		margin-top: 15vh;
		margin-bottom: 4rem;
	}
	.title h2 {
		color: var(--clr-gold);
		font-family: 'Great Vibes', cursive;
		text-align: center;
	}
	.section-center {
		max-width: var(--fixed-width);
	}
	.question {
		background: var(--clr-white);
		border-radius: var(--radius);
		box-shadow: var(--light-shadow);
		padding: 1.5rem 1.5rem 0 1.5rem;
		margin-bottom: 2rem;
	}
	.question-title {
		display: flex;
		justify-content: space-between;
		align-items: center;
		text-transform: capitalize;
		padding-bottom: 1rem;
	}
	.question-title p {
		margin-bottom: 0;
		letter-spacing: var(--spacing);
		color: var(--clr-grey-1);
	}
	.question-btn {
		font-size: 1.5rem;
		background: transparent;
		border-color: transparent;
		cursor: pointer;
		color: var(--clr-gold);
		transition: var(--transition);
	}
	.question-btn:hover {
		transform: rotate(90deg);
	}
	.question-text {
		padding: 1rem 0 1.5rem 0;
		border-top: 1px solid rgba(0, 0, 0, 0.2);
	}
	.question-text p {
		margin-bottom: 0;
	}
	.question-text {
		display: none;
	}
	.minus-icon {
		display: none;
	}

	.show-text .question-text {
		display: block;
	}
	.show-text .minus-icon {
		display: inline;
	}
	.show-text .plus-icon {
		display: none;
	}
</style>
