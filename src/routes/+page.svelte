<script lang="ts">
	import { onMount } from 'svelte';
	import { fade, fly } from 'svelte/transition';
	import { Ratings } from '@skeletonlabs/skeleton';
	import Icon from '@iconify/svelte';
	let visible = false;
	onMount(() => {
		visible = true;
	});
	const bgImages = ['/bg1.jpg', '/bg2.jpeg', '/bg3.webp'];

	const REVIEWS: CustomerReview[] = [
		{
			name: 'Mahindra Agri',
			img: '/images/mahindra-agri-logo.png',
			review:
				'Their commitment to quality and health-conscious farming practices really shines through in these Jumbo Black Seedless grapes. Highly recommended!',
			rating: 4.5
		},
		{
			name: 'Chand Fruits',
			img: '/images/chand-fruits-logo.jpeg',
			review:
				'Their commitment to quality and health-conscious farming practices really shines through in these Jumbo Black Seedless grapes. Highly recommended!',
			rating: 4
		}
	];
</script>

{#if visible}
	<div in:fly={{ y: 200, duration: 2000 }} out:fade>
		<div class="container mx-auto px-4">
			<!-- Existing logo and intro section -->
			<div class="my-8 grid grid-cols-2 gap-4 items-center">
				<div id="logo" class="flex justify-center md:justify-end items-center">
					<div class="flex items-center">
						<img src="/images/logo.svg" alt="Grape icon" class="w-12 h-12 md:w-16 md:h-16 mr-2" />
						<span class="text-5xl md:text-6xl logo-font">TF</span>
					</div>
				</div>
				<div id="intro" class="text-center md:text-left">
					<p class="text-2xl md:text-4xl mb-2">Taware Farms</p>
				</div>
			</div>
		</div>

		<!-- Parallax 1 -->
		<div class="parallax relative" style={`background-image: url(${bgImages[0]});`}>
			<div class="absolute inset-0 flex items-center justify-center">
				<h2
					class="text-lg md:text-3xl uppercase text-white bg-black bg-opacity-30 p-4 rounded md:w-8/12 text-center"
				>
					We are vinegrowers of jumbo black seedless grapes, grown residue-free, delivering
					unmatched quality to discerning customers worldwide.
				</h2>
			</div>
		</div>

		<!-- Customer section -->
		<div class="container mx-auto px-4 my-14">
			<div class="w-full">
				<h2
					class="text-3xl font-bold mb-8 p-2 text-center text-white rounded-xl dark:text-black bg-slate-800 dark:bg-white"
				>
					Our Customers
				</h2>
			</div>
			<div class="mx-auto md:flex flex-wrap justify-center">
				<!-- Customer review cards -->
				{#each REVIEWS as review}
					<div class="card overflow-hidden shadow-lg m-3 max-w-sm flex-grow">
						<header class="bg-gray-100 p-4">
							<img src={review.img} alt="{review.name} logo" class="max-h-48 mx-auto" />
						</header>
						<div class="p-6 space-y-4">
							<Ratings value={review.rating} max={5}>
								<svelte:fragment slot="empty"><Icon icon="ic:round-star-border" /></svelte:fragment>
								<svelte:fragment slot="half"><Icon icon="ic:round-star-half" /></svelte:fragment>
								<svelte:fragment slot="full"><Icon icon="ic:round-star" /></svelte:fragment>
							</Ratings>
							<h3 class="h3 text-center" data-toc-ignore>{review.name}</h3>
							<article>
								<p class="text-gray-600 italic">"{review.review}"</p>
							</article>
						</div>
					</div>
				{/each}
			</div>
		</div>

		<!-- Parallax 2 -->
		<div class="parallax relative" style={`background-image: url(${bgImages[1]});`} />

		<!-- About Us section -->
		<div class="container mx-auto px-4 my-14" id="about-us">
			<div class="w-full">
				<h2
					class="text-3xl font-bold mb-8 p-2 text-center text-white rounded-xl dark:text-black bg-slate-800 dark:bg-white"
				>
					About Taware Farms
				</h2>
			</div>
			<div class="bg-white dark:bg-gray-800 shadow-lg rounded-lg p-6 space-y-4">
				<p class="text-lg">
					Nestled in the heart of Phaltan, Maharashtra, Taware Farms has been a beacon of excellence
					in viniculture for over 5 years. Our journey began in 2019 when our founder, Kumar Taware,
					planted our first grapevines with a vision of producing the finest grapes in India.
				</p>
				<h3 class="text-xl font-semibold">Our Commitment</h3>
				<p>
					At Taware Farms, we specialize in cultivating premium jumbo black seedless grapes. Our
					commitment to quality is unwavering, and it shows in every bunch we produce. We've
					perfected the art of growing grapes that are not just visually appealing but also burst
					with flavor.
				</p>
				<h3 class="text-xl font-semibold">Residue-Free Farming</h3>
				<p>
					We take pride in our residue-free farming practices. This means we cultivate our grapes
					without the use of harmful pesticides or chemicals, ensuring that every grape is as pure
					as nature intended. Our approach not only yields healthier produce but also contributes to
					sustainable agriculture and environmental conservation.
				</p>
			</div>
		</div>

		<!-- Parallax 3 -->
		<div class="parallax relative" style={`background-image: url(${bgImages[2]});`} />

		<!-- Contact Us section -->
		<div class="container mx-auto px-4 my-14" id="contact-us">
			<div class="w-full">
				<h2
					class="text-3xl font-bold mb-8 p-2 text-center text-white rounded-xl dark:text-black bg-slate-800 dark:bg-white"
				>
					Contact Us
				</h2>
			</div>

			<!-- Contact Information -->
			<div class="bg-white dark:bg-gray-800 shadow-lg rounded-lg p-6 space-y-4 md:w-8/12 mx-auto">
				<h3 class="text-xl font-semibold">Get in Touch</h3>
				<p>
					We'd love to hear from you! Whether you have a question about our grapes, want to place an
					order, or are interested in partnering with us, please don't hesitate to reach out.
				</p>

				<div class="space-y-2">
					<p><strong>Address:</strong> Taware Farms, Vinchurni, Phaltan, Maharashtra, India</p>
					<p><strong>Phone:</strong>+91 98222 81461</p>
					<p>
						<strong>Email:</strong> <a href="mailto:info@tawarefarms.com">info@tawarefarms.com</a>
					</p>
					<p><strong>Business Hours:</strong> Sunday - Saturday, 9:00 AM - 8:00 PM</p>
				</div>

				<div class="mt-6">
					<h4 class="text-lg font-semibold mb-2">Follow Us</h4>
					<div class="flex space-x-4">
						<!-- Add your social media icons/links here -->
						<a href="#" class="text-blue-600 hover:text-blue-800">Facebook</a>
						<a href="#" class="text-blue-400 hover:text-blue-600">Twitter</a>
						<a href="#" class="text-pink-600 hover:text-pink-800">Instagram</a>
					</div>
				</div>
			</div>
		</div>
	</div>
{/if}

<style lang="postcss">
	.parallax {
		min-height: 500px;
		background-attachment: fixed;
		background-position: center;
		background-repeat: no-repeat;
		background-size: cover;
	}
</style>
