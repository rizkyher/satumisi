<script>
	import { Button } from '$lib/components/ui/button/index.js';
	import {
		Card,
		CardContent,
		CardDescription,
		CardHeader,
		CardTitle
	} from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';

	const values = [
		{
			title: 'Integritas',
			description:
				'Menjalankan setiap program dengan transparansi dan akuntabilitas penuh kepada masyarakat.',
			icon: '⭐'
		},
		{
			title: 'Kolaborasi',
			description:
				'Bekerja sama dengan berbagai pihak untuk mencapai dampak yang lebih luas dan berkelanjutan.',
			icon: '🤝'
		},
		{
			title: 'Inovasi',
			description:
				'Mengembangkan metode-metode kreatif dalam meningkatkan minat baca dan literasi masyarakat.',
			icon: '💡'
		},
		{
			title: 'Keberlanjutan',
			description: 'Membangun program yang dapat bertahan dan berkembang untuk jangka panjang.',
			icon: '🌱'
		}
	];

	const team = [
		{ name: 'Dr. Ahmad Budiman', role: 'Ketua Umum', image: '👨‍💼' },
		{ name: 'Sarah Wijaya, M.Pd', role: 'Direktur Program', image: '👩‍💼' },
		{ name: 'Rina Kusuma', role: 'Koordinator Relawan', image: '👩‍🏫' },
		{ name: 'Budi Santoso', role: 'Manajer Keuangan', image: '👨‍💻' }
	];

	const timeline = [
		{ year: '2018', event: 'Satu Misi didirikan di Jakarta' },
		{ year: '2019', event: 'Peluncuran program Taman Baca Keliling pertama' },
		{ year: '2020', event: 'Ekspansi ke 10 provinsi di Indonesia' },
		{ year: '2021', event: 'Mencapai 5,000 anak terbantu' },
		{ year: '2022', event: 'Peluncuran program Literasi Digital' },
		{ year: '2023', event: 'Kemitraan dengan 50+ sekolah dan komunitas' },
		{ year: '2024', event: 'Mendapat penghargaan dari Kementerian Pendidikan' },
		{ year: '2025', event: 'Target: 100 desa terjangkau' }
	];
</script>

<svelte:head>
	<title>Tentang Kami - Satu Misi</title>
	<meta
		name="description"
		content="Mengenal lebih dekat Satu Misi dan dedikasi kami untuk generasi Indonesia"
	/>
</svelte:head>

<div class="min-h-screen bg-gradient-to-b from-gray-50 to-white">
	<!-- Hero Section - Matching Home Page Style -->
	<section
		class="relative overflow-hidden bg-gradient-to-br from-gray-900 via-gray-800 to-black py-32 md:py-40"
	>
		<!-- Subtle Wave Pattern -->
		<div class="absolute inset-0 opacity-10">
			<svg
				class="absolute bottom-0 w-full"
				viewBox="0 0 1440 320"
				xmlns="http://www.w3.org/2000/svg"
			>
				<path
					fill="#ffffff"
					fill-opacity="0.3"
					d="M0,96L48,112C96,128,192,160,288,165.3C384,171,480,149,576,133.3C672,117,768,107,864,122.7C960,139,1056,181,1152,181.3C1248,181,1344,139,1392,117.3L1440,96L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"
				></path>
			</svg>
		</div>

		<!-- Floating Book Icons -->
		<div class="absolute inset-0 overflow-hidden">
			<div class="animate-float absolute left-1/4 top-20 text-6xl opacity-5">📖</div>
			<div class="animate-float-delayed absolute right-1/4 top-40 text-5xl opacity-5">📚</div>
			<div class="animate-float-slow absolute bottom-40 left-1/3 text-7xl opacity-5">✏️</div>
		</div>

		<div class="container relative z-10 mx-auto px-4 text-center">
			<Badge
				variant="outline"
				class="hero-badge mb-8 border-white/30 bg-white/10 px-6 py-2 text-xs font-bold tracking-widest text-white/90 backdrop-blur-sm"
			>
				MENGENAL KAMI
			</Badge>

			<h1 class="hero-title mb-8 text-6xl font-black tracking-tight text-white md:text-8xl">
				Tentang Kami
			</h1>

			<div
				class="shadow-red hero-subtitle mx-auto mb-10 h-1 w-40 bg-gradient-to-r from-transparent via-red-500 to-transparent"
			></div>

			<p
				class="hero-description mx-auto max-w-3xl text-2xl font-light leading-relaxed text-gray-300 md:text-3xl"
			>
				Mengenal lebih dekat Satu Misi dan dedikasi kami untuk generasi Indonesia
			</p>
		</div>
	</section>

	<!-- Story Section - Gray Theme with Red Accents -->
	<section class="relative overflow-hidden bg-white py-28">
		<div class="absolute inset-0 bg-gradient-to-b from-gray-50 to-white"></div>

		<div class="container relative mx-auto px-4">
			<div class="mx-auto max-w-5xl">
				<div class="mb-12 text-center">
					<Badge
						class="bg-gradient-to-r from-gray-800 to-black px-5 py-2 text-xs font-bold tracking-widest text-white shadow-lg"
					>
						KISAH KAMI
					</Badge>
				</div>

				<h2
					class="section-title mb-12 text-center text-6xl font-black tracking-tight text-gray-900 md:text-7xl"
				>
					Kisah Kami
				</h2>

				<div
					class="shadow-red mx-auto mb-16 h-1 w-40 rounded-full bg-gradient-to-r from-transparent via-red-500 to-transparent"
				></div>

				<div class="space-y-8 text-xl leading-relaxed text-gray-700">
					<p
						class="fade-in-text rounded-2xl border-2 border-gray-200 bg-white p-8 shadow-lg transition-all hover:border-red-500 hover:shadow-xl"
					>
						Satu Misi lahir dari keprihatinan terhadap rendahnya tingkat literasi di berbagai daerah
						di Indonesia. Didirikan pada tahun 2018 oleh sekelompok pendidik dan aktivis sosial,
						kami memulai perjalanan dengan satu tujuan sederhana: memastikan setiap anak Indonesia
						memiliki akses terhadap buku dan pendidikan berkualitas.
					</p>
					<p
						class="fade-in-text rounded-2xl border-2 border-gray-200 bg-white p-8 shadow-lg transition-all hover:border-red-500 hover:shadow-xl"
					>
						Berawal dari satu perpustakaan keliling kecil di Jakarta, kini kami telah berkembang
						menjadi organisasi yang menjangkau lebih dari 50 desa di seluruh Indonesia. Dengan
						bantuan relawan yang berdedikasi dan dukungan masyarakat, kami terus memperluas
						jangkauan program literasi kami.
					</p>
					<p
						class="fade-in-text rounded-2xl border-2 border-gray-200 bg-white p-8 shadow-lg transition-all hover:border-red-500 hover:shadow-xl"
					>
						Kami percaya bahwa literasi adalah fondasi dari kemajuan bangsa. Melalui berbagai
						program inovatif, kami tidak hanya mendistribusikan buku, tetapi juga membangun
						ekosistem literasi yang berkelanjutan di setiap komunitas yang kami layani.
					</p>
				</div>
			</div>
		</div>
	</section>

	<!-- Values Section - Matching Home Page Cards -->
	<section class="relative overflow-hidden bg-gradient-to-b from-white to-gray-50 py-32">
		<div class="container relative mx-auto px-4">
			<div class="mb-12 text-center">
				<Badge
					variant="secondary"
					class="border border-gray-200 bg-white px-5 py-2 text-xs font-bold tracking-widest text-gray-700 shadow-md"
				>
					NILAI-NILAI KAMI
				</Badge>
			</div>

			<h2
				class="section-title mb-24 text-center text-6xl font-black tracking-tight text-gray-900 md:text-7xl"
			>
				Nilai-Nilai Kami
			</h2>

			<div class="mx-auto grid max-w-7xl grid-cols-1 gap-10 md:grid-cols-2 lg:grid-cols-4">
				{#each values as value, i}
					<Card
						class="program-card-premium group relative overflow-hidden rounded-3xl border-2 border-gray-200 bg-white transition-all duration-700 hover:-translate-y-6 hover:rotate-1 hover:border-red-500 hover:shadow-2xl"
						style="animation-delay: {i * 0.15}s;"
					>
						<!-- Red Accent on Hover -->
						<div
							class="absolute inset-0 bg-gradient-to-br from-red-500/0 to-red-500/0 transition-all duration-700 group-hover:from-red-500/5 group-hover:to-red-500/10"
						></div>

						<!-- Floating Icon Background -->
						<div
							class="absolute -right-8 -top-8 h-32 w-32 rounded-full bg-gradient-to-br from-gray-900/5 to-red-500/5 blur-2xl transition-all duration-700 group-hover:scale-150"
						></div>

						<!-- Top Red Line -->
						<div
							class="absolute left-0 right-0 top-0 h-1 bg-red-500 opacity-0 transition-opacity duration-700 group-hover:opacity-100"
						></div>

						<CardHeader class="relative p-8">
							<div
								class="relative mb-8 inline-block transition-all duration-700 group-hover:rotate-12 group-hover:scale-125"
							>
								<div class="text-7xl">{value.icon}</div>
								<div
									class="absolute -inset-4 -z-10 rounded-full bg-red-500/0 blur-xl transition-all duration-700 group-hover:bg-red-500/20"
								></div>
							</div>

							<CardTitle
								class="mb-4 text-2xl font-black text-gray-900 transition-colors duration-300"
							>
								{value.title}
							</CardTitle>

							<div
								class="h-1 w-20 rounded-full bg-gray-300 transition-all duration-700 group-hover:w-full group-hover:bg-red-500"
							></div>
						</CardHeader>

						<CardContent class="relative p-8 pt-0">
							<CardDescription class="text-base leading-relaxed text-gray-600">
								{value.description}
							</CardDescription>
						</CardContent>

						<!-- Corner Decoration -->
						<div
							class="absolute bottom-0 right-0 h-20 w-20 translate-x-10 translate-y-10 rounded-full border-4 border-red-500/0 transition-all duration-700 group-hover:translate-x-8 group-hover:translate-y-8 group-hover:border-red-500/20"
						></div>
					</Card>
				{/each}
			</div>
		</div>
	</section>

	<!-- Timeline Section - Enhanced with Home Page Style -->
	<section class="relative overflow-hidden bg-gradient-to-b from-gray-50 to-white py-32">
		<div class="container relative mx-auto px-4">
			<div class="mb-16 text-center">
				<Badge
					variant="secondary"
					class="border border-gray-200 bg-white px-5 py-2 text-xs font-bold tracking-widest text-gray-700 shadow-md"
				>
					PERJALANAN KAMI
				</Badge>
			</div>

			<h2
				class="section-title mb-24 text-center text-6xl font-black tracking-tight text-gray-900 md:text-7xl"
			>
				Perjalanan Kami
			</h2>

			<div class="mx-auto max-w-5xl">
				<!-- Mobile Timeline -->
				<div class="block md:hidden">
					{#each timeline as item, i}
						<div class="timeline-item relative mb-8 pl-12" style="animation-delay: {i * 0.1}s;">
							<div
								class="absolute left-0 top-2 h-8 w-8 rounded-full border-4 border-white bg-red-500 shadow-lg"
							></div>
							{#if i < timeline.length - 1}
								<div class="absolute left-4 top-10 h-full w-0.5 -translate-x-1/2 bg-gray-300"></div>
							{/if}
							<div
								class="rounded-2xl border-2 border-gray-200 bg-white p-6 shadow-xl transition-all duration-300 hover:scale-105 hover:border-red-500"
							>
								<div class="mb-2 text-2xl font-black text-gray-900">{item.year}</div>
								<p class="font-medium text-gray-700">{item.event}</p>
							</div>
						</div>
					{/each}
				</div>

				<!-- Desktop Timeline -->
				<div class="relative hidden md:block">
					<!-- Vertical Line -->
					<div
						class="absolute bottom-0 left-1/2 top-0 w-1 -translate-x-1/2 transform bg-gradient-to-b from-gray-300 via-red-500 to-gray-300"
					></div>

					{#each timeline as item, i}
						<div
							class="timeline-item relative mb-12 grid grid-cols-2 gap-8"
							style="animation-delay: {i * 0.1}s;"
						>
							{#if i % 2 === 0}
								<div class="text-right">
									<div
										class="inline-block rounded-2xl border-2 border-gray-200 bg-white p-6 shadow-xl transition-all duration-300 hover:scale-105 hover:border-red-500"
									>
										<div class="mb-2 text-3xl font-black text-gray-900">{item.year}</div>
										<p class="font-medium text-gray-700">{item.event}</p>
									</div>
								</div>
								<div></div>
							{:else}
								<div></div>
								<div class="text-left">
									<div
										class="inline-block rounded-2xl border-2 border-gray-200 bg-white p-6 shadow-xl transition-all duration-300 hover:scale-105 hover:border-red-500"
									>
										<div class="mb-2 text-3xl font-black text-gray-900">{item.year}</div>
										<p class="font-medium text-gray-700">{item.event}</p>
									</div>
								</div>
							{/if}

							<div
								class="absolute left-1/2 top-4 h-6 w-6 -translate-x-1/2 rounded-full border-4 border-white bg-red-500 shadow-lg"
							></div>
						</div>
					{/each}
				</div>
			</div>
		</div>
	</section>

	<!-- Team Section - Matching Home Page Cards -->
	<section class="relative overflow-hidden bg-white py-32">
		<div class="container relative mx-auto px-4">
			<div class="mb-12 text-center">
				<Badge
					class="bg-gradient-to-r from-gray-800 to-black px-5 py-2 text-xs font-bold tracking-widest text-white shadow-lg"
				>
					TIM KAMI
				</Badge>
			</div>

			<h2
				class="section-title mb-24 text-center text-6xl font-black tracking-tight text-gray-900 md:text-7xl"
			>
				Tim Kami
			</h2>

			<div class="mx-auto grid max-w-6xl grid-cols-1 gap-10 md:grid-cols-2 lg:grid-cols-4">
				{#each team as member, i}
					<Card
						class="testimonial-card group relative overflow-hidden rounded-3xl border-2 border-gray-200 bg-white text-center transition-all duration-700 hover:-translate-y-6 hover:border-red-500 hover:shadow-2xl"
						style="animation-delay: {i * 0.1}s;"
					>
						<!-- Red Accent on Hover -->
						<div
							class="absolute inset-0 bg-gradient-to-br from-red-500/0 to-red-500/0 transition-all duration-700 group-hover:from-red-500/5 group-hover:to-red-500/10"
						></div>

						<!-- Circular Background Glow -->
						<div
							class="absolute left-1/2 top-20 h-40 w-40 -translate-x-1/2 rounded-full bg-gradient-to-br from-gray-900/5 to-red-500/5 blur-3xl transition-all duration-700 group-hover:scale-150"
						></div>

						<!-- Top Red Line -->
						<div
							class="absolute left-0 right-0 top-0 h-1 bg-red-500 opacity-0 transition-opacity duration-700 group-hover:opacity-100"
						></div>

						<CardHeader class="relative pb-3 pt-8">
							<div class="relative inline-block transition-all duration-700 group-hover:scale-125">
								<div class="mb-6 text-8xl">{member.image}</div>
								<div
									class="absolute -inset-6 -z-10 rounded-full bg-red-500/0 blur-2xl transition-all duration-700 group-hover:bg-red-500/10"
								></div>
							</div>
						</CardHeader>

						<CardContent class="relative px-6 pb-8">
							<h3 class="mb-3 text-xl font-black text-gray-900 transition-colors duration-300">
								{member.name}
							</h3>
							<div
								class="mx-auto mb-4 h-1 w-16 rounded-full bg-gray-300 transition-all duration-700 group-hover:w-full group-hover:bg-red-500"
							></div>
							<Badge
								class="bg-gradient-to-r from-gray-800 to-black px-4 py-2 text-white transition-all duration-300 hover:from-red-600 hover:to-red-700 hover:shadow-lg"
							>
								{member.role}
							</Badge>
						</CardContent>

						<!-- Decorative Corners -->
						<div
							class="absolute left-0 top-0 h-3 w-3 -translate-x-1 -translate-y-1 rounded-full border-2 border-red-500/0 transition-all duration-700 group-hover:translate-x-2 group-hover:translate-y-2 group-hover:border-red-500/50"
						></div>
						<div
							class="absolute right-0 top-0 h-3 w-3 -translate-y-1 translate-x-1 rounded-full border-2 border-red-500/0 transition-all duration-700 group-hover:-translate-x-2 group-hover:translate-y-2 group-hover:border-red-500/50"
						></div>
					</Card>
				{/each}
			</div>
		</div>
	</section>

	<!-- CTA Section - Matching Home Page Dark Theme -->
	<section
		class="relative overflow-hidden bg-gradient-to-br from-gray-900 via-gray-800 to-black py-40"
	>
		<!-- Wave Pattern -->
		<div class="absolute inset-0 opacity-5">
			<svg class="absolute top-0 w-full" viewBox="0 0 1440 320" xmlns="http://www.w3.org/2000/svg">
				<path
					fill="#ffffff"
					fill-opacity="0.3"
					d="M0,96L48,112C96,128,192,160,288,165.3C384,171,480,149,576,133.3C672,117,768,107,864,122.7C960,139,1056,181,1152,181.3C1248,181,1344,139,1392,117.3L1440,96L1440,0L1392,0C1344,0,1248,0,1152,0C1056,0,960,0,864,0C768,0,672,0,576,0C480,0,384,0,288,0C192,0,96,0,48,0L0,0Z"
				></path>
			</svg>
		</div>

		<div class="container relative z-10 mx-auto px-4 text-center">
			<div class="mx-auto max-w-4xl">
				<Badge
					variant="outline"
					class="mb-10 border-white/30 bg-white/10 px-6 py-2 text-xs font-bold tracking-widest text-white/90 backdrop-blur-sm"
				>
					MARI BERGABUNG
				</Badge>

				<h2 class="mb-12 text-5xl font-black tracking-tight text-white md:text-7xl">
					Ingin Tahu Lebih Lanjut?
				</h2>

				<div
					class="shadow-red mx-auto mb-12 h-1 w-40 rounded-full bg-gradient-to-r from-transparent via-red-500 to-transparent"
				></div>

				<p class="mx-auto mb-16 max-w-3xl text-2xl font-light leading-relaxed text-gray-300">
					Hubungi kami untuk informasi lebih lanjut atau untuk bergabung dengan misi kami
				</p>

				<div class="flex flex-col justify-center gap-6 sm:flex-row">
					<Button
						size="lg"
						class="group relative overflow-hidden border-2 border-white bg-white px-12 py-7 text-lg font-bold text-black shadow-2xl transition-all duration-500 hover:scale-110 hover:bg-gray-100"
					>
						<span class="relative z-10 flex items-center gap-2">
							Hubungi Kami
							<span class="transition-transform duration-300 group-hover:translate-x-2">✉️</span>
						</span>
					</Button>

					<Button
						size="lg"
						class="group relative overflow-hidden border-2 border-red-500 bg-red-500 px-12 py-7 text-lg font-bold text-white shadow-2xl transition-all duration-500 hover:scale-110 hover:border-red-600 hover:bg-red-600"
					>
						<span class="relative z-10 flex items-center gap-2">
							Bergabung Sekarang
							<span class="transition-transform duration-300 group-hover:scale-125">🤝</span>
						</span>
					</Button>
				</div>
			</div>
		</div>
	</section>
</div>

<style>
	@keyframes fade-in-up {
		from {
			opacity: 0;
			transform: translateY(30px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	@keyframes float {
		0%,
		100% {
			transform: translate(0, 0) rotate(0deg);
		}
		33% {
			transform: translate(30px, -30px) rotate(5deg);
		}
		66% {
			transform: translate(-20px, 20px) rotate(-5deg);
		}
	}

	@keyframes float-delayed {
		0%,
		100% {
			transform: translate(0, 0) rotate(0deg);
		}
		33% {
			transform: translate(-30px, 30px) rotate(-5deg);
		}
		66% {
			transform: translate(20px, -20px) rotate(5deg);
		}
	}

	@keyframes float-slow {
		0%,
		100% {
			transform: translate(0, 0) scale(1);
		}
		50% {
			transform: translate(20px, 20px) scale(1.1);
		}
	}

	@keyframes card-appear {
		from {
			opacity: 0;
			transform: translateY(50px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	@keyframes timeline-appear {
		from {
			opacity: 0;
			transform: translateX(-50px);
		}
		to {
			opacity: 1;
			transform: translateX(0);
		}
	}

	@keyframes testimonial-appear {
		from {
			opacity: 0;
			transform: scale(0.9) translateY(30px);
		}
		to {
			opacity: 1;
			transform: scale(1) translateY(0);
		}
	}

	/* Animation Classes */
	.hero-badge {
		animation: fade-in-up 0.8s ease-out 0.3s forwards;
		opacity: 0;
	}

	.hero-title {
		animation: fade-in-up 1s ease-out 0.5s forwards;
		opacity: 0;
	}

	.hero-subtitle {
		animation: fade-in-up 1s ease-out 0.7s forwards;
		opacity: 0;
	}

	.hero-description {
		animation: fade-in-up 1s ease-out 0.9s forwards;
		opacity: 0;
	}

	.animate-float {
		animation: float 20s ease-in-out infinite;
	}

	.animate-float-delayed {
		animation: float-delayed 25s ease-in-out infinite;
	}

	.animate-float-slow {
		animation: float-slow 30s ease-in-out infinite;
	}

	.fade-in-text {
		animation: fade-in-up 1s ease-out forwards;
	}

	.timeline-item {
		animation: timeline-appear 0.8s ease-out forwards;
		opacity: 0;
	}

	.program-card-premium {
		animation: card-appear 0.8s ease-out forwards;
		opacity: 0;
	}

	.testimonial-card {
		animation: testimonial-appear 0.8s ease-out forwards;
		opacity: 0;
	}

	.section-title {
		animation: fade-in-up 1s ease-out forwards;
	}

	.shadow-red {
		box-shadow:
			0 0 20px rgba(239, 68, 68, 0.5),
			0 0 40px rgba(239, 68, 68, 0.3);
	}

	/* Smooth scroll */
	:global(html) {
		scroll-behavior: smooth;
	}

	/* Focus styles */
	:global(button:focus-visible) {
		outline: 3px solid rgba(239, 68, 68, 0.5);
		outline-offset: 4px;
	}

	/* Custom scrollbar - Gray with Red */
	:global(::-webkit-scrollbar) {
		width: 12px;
	}

	:global(::-webkit-scrollbar-track) {
		background: #f3f4f6;
	}

	:global(::-webkit-scrollbar-thumb) {
		background: linear-gradient(180deg, #4b5563, #ef4444);
		border-radius: 6px;
	}

	:global(::-webkit-scrollbar-thumb:hover) {
		background: linear-gradient(180deg, #374151, #dc2626);
	}

	/* Text selection - Red accent */
	:global(::selection) {
		background-color: rgba(239, 68, 68, 0.2);
		color: inherit;
	}

	/* Reduce Motion */
	@media (prefers-reduced-motion: reduce) {
		*,
		*::before,
		*::after {
			animation-duration: 0.01ms !important;
			animation-iteration-count: 1 !important;
			transition-duration: 0.01ms !important;
		}
	}

	/* Responsive Typography */
	@media (max-width: 768px) {
		.hero-title {
			font-size: 3.5rem;
		}

		.section-title {
			font-size: 2.5rem;
		}
	}
</style>
