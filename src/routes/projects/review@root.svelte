<script lang="ts">
	import { onMount } from 'svelte';
	import person from '../../assets/person-1.jpeg';
	type review = {
		id: number;
		name: string;
		job: string;
		img: string;
		text: string;
	};

	let curIdx: number;
	export let review: review;

	$: curIdx = 0;
	$: review = {
		id: 0,
		name: 'sara jones',
		job: 'ux designer',
		img: person,
		text: 'lorem ipsum'
	};

	const reviews: review[] = [
		{
			id: 1,
			name: 'susan smith',
			job: 'web developer',
			img: 'https://res.cloudinary.com/diqqf3eq2/image/upload/v1586883334/person-1_rfzshl.jpg',
			text: "I'm baby meggings twee health goth +1. Bicycle rights tumeric chartreuse before they sold out chambray pop-up. Shaman humblebrag pickled coloring book salvia hoodie, cold-pressed four dollar toast everyday carry"
		},
		{
			id: 2,
			name: 'anna johnson',
			job: 'web designer',
			img: 'https://res.cloudinary.com/diqqf3eq2/image/upload/v1586883409/person-2_np9x5l.jpg',
			text: 'Helvetica artisan kinfolk thundercats lumbersexual blue bottle. Disrupt glossier gastropub deep v vice franzen hell of brooklyn twee enamel pin fashion axe.photo booth jean shorts artisan narwhal.'
		},
		{
			id: 3,
			name: 'peter jones',
			job: 'intern',
			img: 'https://res.cloudinary.com/diqqf3eq2/image/upload/v1586883417/person-3_ipa0mj.jpg',
			text: 'Sriracha literally flexitarian irony, vape marfa unicorn. Glossier tattooed 8-bit, fixie waistcoat offal activated charcoal slow-carb marfa hell of pabst raclette post-ironic jianbing swag.'
		},
		{
			id: 4,
			name: 'bill anderson',
			job: 'the boss',
			img: 'https://res.cloudinary.com/diqqf3eq2/image/upload/v1586883423/person-4_t9nxjt.jpg',
			text: 'Edison bulb put a bird on it humblebrag, marfa pok pok heirloom fashion axe cray stumptown venmo actually seitan. VHS farm-to-table schlitz, edison bulb pop-up 3 wolf moon tote bag street art shabby chic. '
		}
	];
	onMount(() => {
		//btn
		const prevBtn = document.querySelector<HTMLButtonElement>('.prev-btn') as HTMLButtonElement;
		const nextBtn = document.querySelector<HTMLButtonElement>('.next-btn') as HTMLButtonElement;
		const randomBtn = document.querySelector<HTMLButtonElement>('.random-btn') as HTMLButtonElement;

		prevBtn.addEventListener('click', () => {
			curIdx--;
			if (curIdx < 0) {
				curIdx = reviews.length - 1;
			}
		});

		nextBtn.addEventListener('click', () => {
			curIdx++;
			if (curIdx > reviews.length - 1) {
				curIdx = 0;
			}
		});

		randomBtn.addEventListener('click', () => {
			curIdx = Math.floor(Math.random() * reviews.length);
		});
	});

	$: review = reviews[curIdx];
</script>

<main>
	<section class="container">
		<!-- title  -->
		<div class="title">
			<h2>our reviews</h2>
			<div class="underline" />
		</div>
		<!-- end of title  -->
		<!-- review  -->
		<article class="review">
			<div class="img-container">
				<img src={review.img} alt="person" id="person-img" />
			</div>
			<h4 id="author">{review.name}</h4>
			<p id="job">{review.job}</p>
			<p id="info">
				{review.text}
			</p>
			<!-- prev next button  -->
			<div class="button-container">
				<button class="prev-btn">prev</button>
				<button class="next-btn">next</button>
			</div>
			<!-- end of prev next button  -->
			<!-- random button  -->
			<button class="random-btn">suprise me</button>
		</article>
	</section>
</main>

<style>
	main {
		min-height: calc(100vh - 3rem);
		display: grid;
		place-items: center;
	}
	.title {
		text-align: center;
		margin-bottom: 4rem;
	}
	.underline {
		height: 0.25rem;
		width: 5rem;
		background: var(--clr-primary-5);
		margin: 0 auto;
	}
	.container {
		width: 80vw;
		max-width: var(--fixed-witdh);
	}
	.review {
		background: var(--clr-white);
		padding: 1.5rem 2rem;
		border-radius: var(--radius);
		box-shadow: var(--light-shadow);
		transition: var(--transition);
		text-align: center;
	}
	.review:hover {
		box-shadow: var(--dark-shadow);
	}
	.img-container {
		position: relative;
		width: 150px;
		height: 150px;
		border-radius: 50%;
		margin: 0 auto;
		margin-bottom: 1.5rem;
	}

	#person-img {
		width: 100%;
		height: 100%;
		display: block;
		object-fit: cover;
		border-radius: 50%;
		position: relative;
	}

	.img-container::after {
		font-weight: 900;
		content: '\f10e';
		position: absolute;
		top: 0;
		left: 0;
		width: 2.5rem;
		height: 2.5rem;
		display: grid;
		place-items: center;
		border-radius: 50%;
		transform: translateY(25%);
		background: var(--clr-primary-5);
		color: var(--clr-white);
	}
	.img-container::before {
		content: '';
		width: 100%;
		height: 100%;
		background: var(--clr-primary-5);
		position: absolute;
		top: -0.25rem;
		right: -0.5rem;
		border-radius: 50%;
	}
	#author {
		margin-bottom: 0.25rem;
	}
	#info {
		margin-bottom: 0.75rem;
	}
	.prev-btn,
	.next-btn {
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

	.prev-btn:hover,
	.next-btn:hover {
		color: var(--clr-primary-5);
	}

	.random-btn {
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
	.random-btn:hover {
		background: var(--clr-primary-5);
		color: var(--clr-primary-1);
	}
</style>
