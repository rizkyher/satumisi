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

	const missions = [
		{
			number: '01',
			title: 'Meningkatkan Akses Literasi',
			description:
				'Menyediakan akses terhadap buku dan bahan bacaan berkualitas bagi masyarakat di daerah terpencil dan kurang terlayani.',
			icon: '📚'
		},
		{
			number: '02',
			title: 'Pemberdayaan Pendidik',
			description:
				'Melatih dan memberdayakan guru serta relawan untuk menjadi agen perubahan dalam meningkatkan literasi di komunitas mereka.',
			icon: '👨‍🏫'
		},
		{
			number: '03',
			title: 'Membangun Ekosistem Literasi',
			description:
				'Menciptakan lingkungan yang kondusif untuk budaya membaca melalui pembentukan taman baca dan komunitas literasi.',
			icon: '🌳'
		},
		{
			number: '04',
			title: 'Inovasi Pembelajaran',
			description:
				'Mengembangkan metode pembelajaran yang kreatif, menyenangkan, dan sesuai dengan kebutuhan zaman digital.',
			icon: '💡'
		},
		{
			number: '05',
			title: 'Kolaborasi Strategis',
			description:
				'Membangun kemitraan dengan pemerintah, sekolah, komunitas, dan sektor swasta untuk memperluas dampak program.',
			icon: '🤝'
		},
		{
			number: '06',
			title: 'Literasi Digital',
			description:
				'Mempersiapkan generasi muda dengan keterampilan literasi digital dan media untuk menghadapi era informasi.',
			icon: '💻'
		}
	];

	const goals = [
		{
			title: 'Jangkauan Nasional',
			target: '100+ Desa',
			description: 'Menjangkau minimal 100 desa di seluruh Indonesia pada tahun 2025',
			icon: '🎯'
		},
		{
			title: 'Dampak Literasi',
			target: '20,000+ Anak',
			description: 'Meningkatkan kemampuan literasi 20,000+ anak Indonesia',
			icon: '📖'
		},
		{
			title: 'Perpustakaan Keliling',
			target: '50 Unit',
			description: 'Mengoperasikan 50 unit perpustakaan keliling di berbagai daerah',
			icon: '🚐'
		},
		{
			title: 'Relawan Aktif',
			target: '500+ Relawan',
			description: 'Memiliki jaringan 500+ relawan terlatih dan berdedikasi',
			icon: '🤝'
		}
	];

	const principles = [
		{
			icon: '🎯',
			title: 'Berfokus pada Dampak',
			description:
				'Setiap program dirancang dengan tujuan jelas dan terukur untuk memastikan dampak nyata bagi masyarakat.'
		},
		{
			icon: '🌍',
			title: 'Inklusif dan Merata',
			description:
				'Memberikan perhatian khusus pada daerah terpencil dan komunitas yang paling membutuhkan.'
		},
		{
			icon: '🔄',
			title: 'Berkelanjutan',
			description:
				'Membangun kapasitas lokal agar program dapat terus berjalan dan berkembang tanpa ketergantungan.'
		},
		{
			icon: '✨',
			title: 'Berbasis Komunitas',
			description:
				'Melibatkan masyarakat lokal dalam setiap tahap program untuk memastikan relevansi dan keberlanjutan.'
		}
	];
</script>

<svelte:head>
	<title>Visi & Misi - Satu Misi</title>
	<meta
		name="description"
		content="Arah dan tujuan kami dalam membangun Indonesia yang lebih literat"
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

		<!-- Floating Icons -->
		<div class="absolute inset-0 overflow-hidden">
			<div class="animate-float absolute left-1/4 top-20 text-6xl opacity-5">🎯</div>
			<div class="animate-float-delayed absolute right-1/4 top-40 text-5xl opacity-5">💡</div>
			<div class="animate-float-slow absolute bottom-40 left-1/3 text-7xl opacity-5">🌟</div>
		</div>

		<div class="container relative z-10 mx-auto px-4 text-center">
			<Badge
				variant="outline"
				class="hero-badge mb-8 border-white/30 bg-white/10 px-6 py-2 text-xs font-bold tracking-widest text-white/90 backdrop-blur-sm"
			>
				ARAH & TUJUAN
			</Badge>

			<h1 class="hero-title mb-8 text-6xl font-black tracking-tight text-white md:text-8xl">
				Visi & Misi
			</h1>

			<div
				class="shadow-red hero-subtitle mx-auto mb-10 h-1 w-40 bg-gradient-to-r from-transparent via-red-500 to-transparent"
			></div>

			<p
				class="hero-description mx-auto max-w-3xl text-2xl font-light leading-relaxed text-gray-300 md:text-3xl"
			>
				Arah dan tujuan kami dalam membangun Indonesia yang lebih literat
			</p>
		</div>
	</section>

	<!-- Vision Section - Enhanced with Visual Elements -->
	<section class="relative overflow-hidden bg-white py-32">
		<div class="absolute inset-0 bg-gradient-to-b from-gray-50 to-white"></div>

		<!-- Decorative Elements -->
		<div class="absolute left-0 top-40 h-96 w-96 rounded-full bg-red-500/5 blur-3xl"></div>
		<div class="absolute bottom-40 right-0 h-96 w-96 rounded-full bg-gray-900/5 blur-3xl"></div>

		<div class="container relative mx-auto px-4">
			<div class="mx-auto max-w-5xl">
				<div class="mb-12 text-center">
					<Badge
						class="mb-8 bg-gradient-to-r from-gray-800 to-black px-5 py-2 text-xs font-bold tracking-widest text-white shadow-lg"
					>
						VISI
					</Badge>
				</div>

				<div class="group relative">
					<!-- Glow Effect -->
					<div
						class="absolute -inset-4 rounded-3xl bg-gradient-to-br from-red-500/10 to-gray-900/10 opacity-0 blur-2xl transition-opacity duration-700 group-hover:opacity-100"
					></div>

					<div
						class="relative rounded-3xl border-2 border-gray-200 bg-white p-12 shadow-xl transition-all duration-500 group-hover:border-red-500 group-hover:shadow-2xl md:p-16"
					>
						<!-- Top Red Line -->
						<div
							class="absolute left-0 right-0 top-0 h-1 bg-red-500 opacity-0 transition-opacity duration-700 group-hover:opacity-100"
						></div>

						<div class="mb-8 text-center text-7xl">🎯</div>

						<h2
							class="mb-8 text-center text-3xl font-black leading-relaxed text-gray-900 md:text-4xl lg:text-5xl"
						>
							Menjadi Gerakan Literasi Terdepan yang Memberdayakan Setiap Generasi Indonesia untuk
							Mencapai Potensi Penuh Mereka Melalui Akses Terhadap Pendidikan dan Bahan Bacaan
							Berkualitas
						</h2>

						<div
							class="mx-auto mb-8 h-1 w-32 rounded-full bg-gray-300 transition-all duration-500 group-hover:w-64 group-hover:bg-red-500"
						></div>

						<p class="text-center text-xl leading-relaxed text-gray-700">
							Kami membayangkan Indonesia di mana setiap anak, tanpa memandang latar belakang atau
							lokasi geografis, memiliki kesempatan yang sama untuk mengembangkan kemampuan literasi
							dan meraih masa depan yang cerah.
						</p>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Mission Section - Premium Cards -->
	<section class="relative overflow-hidden bg-gradient-to-b from-white to-gray-50 py-32">
		<div class="container relative mx-auto px-4">
			<div class="mb-16 text-center">
				<Badge
					variant="secondary"
					class="mb-6 border border-gray-200 bg-white px-5 py-2 text-xs font-bold tracking-widest text-gray-700 shadow-md"
				>
					MISI
				</Badge>
				<h2 class="mb-12 text-6xl font-black tracking-tight text-gray-900 md:text-7xl">
					Langkah Strategis Kami
				</h2>
				<div
					class="shadow-red mx-auto mb-8 h-1 w-40 rounded-full bg-gradient-to-r from-transparent via-red-500 to-transparent"
				></div>
				<p class="mx-auto max-w-2xl text-xl text-gray-600">
					Untuk mewujudkan visi kami, berikut adalah misi yang kami jalankan
				</p>
			</div>

			<div class="mx-auto grid max-w-7xl grid-cols-1 gap-10 md:grid-cols-2 lg:grid-cols-3">
				{#each missions as mission, i}
					<Card
						class="mission-card group relative overflow-hidden rounded-3xl border-2 border-gray-200 bg-white transition-all duration-700 hover:-translate-y-6 hover:border-red-500 hover:shadow-2xl"
						style="animation-delay: {i * 0.1}s;"
					>
						<!-- Red Accent on Hover -->
						<div
							class="absolute inset-0 bg-gradient-to-br from-red-500/0 to-red-500/0 transition-all duration-700 group-hover:from-red-500/5 group-hover:to-red-500/10"
						></div>

						<!-- Top Red Line -->
						<div
							class="absolute left-0 right-0 top-0 h-1 bg-red-500 opacity-0 transition-opacity duration-700 group-hover:opacity-100"
						></div>

						<CardHeader class="relative">
							<div class="mb-4 flex items-start gap-4">
								<div class="relative">
									<div
										class="text-5xl transition-all duration-700 group-hover:rotate-12 group-hover:scale-125"
									>
										{mission.icon}
									</div>
									<div
										class="absolute -inset-4 -z-10 rounded-full bg-red-500/0 blur-xl transition-all duration-700 group-hover:bg-red-500/20"
									></div>
								</div>
								<div
									class="rounded-lg bg-gray-100 px-3 py-1 text-2xl font-black text-gray-400 transition-all duration-500 group-hover:bg-red-500 group-hover:text-white"
								>
									{mission.number}
								</div>
							</div>
							<CardTitle class="text-2xl font-black text-gray-900">
								{mission.title}
							</CardTitle>
							<div
								class="h-1 w-12 rounded-full bg-gray-300 transition-all duration-500 group-hover:w-24 group-hover:bg-red-500"
							></div>
						</CardHeader>
						<CardContent class="relative">
							<CardDescription class="text-base leading-relaxed text-gray-600">
								{mission.description}
							</CardDescription>
						</CardContent>

						<!-- Corner Decoration -->
						<div
							class="absolute bottom-0 right-0 h-16 w-16 translate-x-8 translate-y-8 rounded-full border-4 border-red-500/0 transition-all duration-700 group-hover:translate-x-6 group-hover:translate-y-6 group-hover:border-red-500/20"
						></div>
					</Card>
				{/each}
			</div>
		</div>
	</section>

	<!-- Strategic Goals Section - Dark Cards with Icons -->
	<section class="relative overflow-hidden bg-white py-32">
		<div class="container relative mx-auto px-4">
			<div class="mb-16 text-center">
				<Badge
					class="mb-6 bg-gradient-to-r from-gray-800 to-black px-5 py-2 text-xs font-bold tracking-widest text-white shadow-lg"
				>
					TARGET 2025
				</Badge>
				<h2 class="mb-12 text-6xl font-black tracking-tight text-gray-900 md:text-7xl">
					Target Strategis 2025
				</h2>
				<div
					class="shadow-red mx-auto mb-8 h-1 w-40 rounded-full bg-gradient-to-r from-transparent via-red-500 to-transparent"
				></div>
				<p class="mx-auto max-w-2xl text-xl text-gray-600">
					Sasaran konkret yang ingin kami capai dalam perjalanan mewujudkan visi
				</p>
			</div>

			<div class="mx-auto grid max-w-6xl grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-4">
				{#each goals as goal, i}
					<Card
						class="goal-card group relative overflow-hidden rounded-3xl border-2 border-gray-200 bg-gradient-to-br from-gray-900 via-gray-800 to-black text-white transition-all duration-700 hover:-translate-y-4 hover:border-red-500 hover:shadow-2xl"
						style="animation-delay: {i * 0.1}s;"
					>
						<!-- Background Pattern -->
						<div class="absolute inset-0 opacity-5">
							<div class="absolute right-0 top-0 h-32 w-32 rounded-full bg-white blur-2xl"></div>
						</div>

						<!-- Top Red Line -->
						<div
							class="absolute left-0 right-0 top-0 h-1 bg-red-500 opacity-0 transition-opacity duration-700 group-hover:opacity-100"
						></div>

						<CardHeader class="relative pb-3 text-center">
							<div class="mb-4">
								<div
									class="text-6xl transition-all duration-700 group-hover:rotate-12 group-hover:scale-125"
								>
									{goal.icon}
								</div>
								<div
									class="absolute inset-0 -z-10 rounded-full bg-red-500/0 blur-2xl transition-all duration-700 group-hover:bg-red-500/20"
								></div>
							</div>
							<CardTitle class="text-lg font-semibold text-white/90">{goal.title}</CardTitle>
						</CardHeader>
						<CardContent class="relative text-center">
							<div class="my-4 text-4xl font-black text-white">{goal.target}</div>
							<div
								class="mx-auto mb-4 h-1 w-16 rounded-full bg-white/30 transition-all duration-500 group-hover:w-full group-hover:bg-red-500"
							></div>
							<p class="text-sm leading-relaxed text-white/70">{goal.description}</p>
						</CardContent>
					</Card>
				{/each}
			</div>
		</div>
	</section>

	<!-- Principles Section - 2x2 Grid -->
	<section class="relative overflow-hidden bg-gradient-to-b from-white to-gray-50 py-32">
		<div class="container relative mx-auto px-4">
			<div class="mx-auto max-w-5xl">
				<div class="mb-16 text-center">
					<Badge
						variant="secondary"
						class="mb-6 border border-gray-200 bg-white px-5 py-2 text-xs font-bold tracking-widest text-gray-700 shadow-md"
					>
						PRINSIP KAMI
					</Badge>
					<h2 class="mb-12 text-6xl font-black tracking-tight text-gray-900 md:text-7xl">
						Prinsip Kerja Kami
					</h2>
					<div
						class="shadow-red mx-auto mb-8 h-1 w-40 rounded-full bg-gradient-to-r from-transparent via-red-500 to-transparent"
					></div>
				</div>

				<div class="grid grid-cols-1 gap-8 md:grid-cols-2">
					{#each principles as principle, i}
						<Card
							class="principle-card group relative overflow-hidden rounded-3xl border-2 border-gray-200 bg-white transition-all duration-700 hover:-translate-y-4 hover:border-red-500 hover:shadow-2xl"
							style="animation-delay: {i * 0.1}s;"
						>
							<!-- Red Accent on Hover -->
							<div
								class="absolute inset-0 bg-gradient-to-br from-red-500/0 to-red-500/0 transition-all duration-700 group-hover:from-red-500/5 group-hover:to-red-500/10"
							></div>

							<!-- Top Red Line -->
							<div
								class="absolute left-0 right-0 top-0 h-1 bg-red-500 opacity-0 transition-opacity duration-700 group-hover:opacity-100"
							></div>

							<CardHeader class="relative">
								<div class="flex items-start gap-4">
									<div class="relative">
										<div
											class="text-5xl transition-all duration-700 group-hover:rotate-12 group-hover:scale-125"
										>
											{principle.icon}
										</div>
										<div
											class="absolute -inset-4 -z-10 rounded-full bg-red-500/0 blur-xl transition-all duration-700 group-hover:bg-red-500/20"
										></div>
									</div>
									<CardTitle class="pt-1 text-2xl font-black text-gray-900">
										{principle.title}
									</CardTitle>
								</div>
							</CardHeader>
							<CardContent class="relative">
								<div
									class="mb-4 h-1 w-12 rounded-full bg-gray-300 transition-all duration-500 group-hover:w-24 group-hover:bg-red-500"
								></div>
								<p class="leading-relaxed text-gray-700">
									{principle.description}
								</p>
							</CardContent>
						</Card>
					{/each}
				</div>
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
					MARI BERSAMA
				</Badge>

				<h2 class="mb-12 text-5xl font-black tracking-tight text-white md:text-7xl">
					Mari Wujudkan Visi Bersama
				</h2>

				<div
					class="shadow-red mx-auto mb-12 h-1 w-40 rounded-full bg-gradient-to-r from-transparent via-red-500 to-transparent"
				></div>

				<p class="mx-auto mb-16 max-w-3xl text-2xl font-light leading-relaxed text-gray-300">
					Bergabunglah dengan kami dalam misi mencerdaskan generasi Indonesia
				</p>

				<div class="flex flex-col justify-center gap-6 sm:flex-row">
					<Button
						size="lg"
						class="group relative overflow-hidden border-2 border-white bg-white px-12 py-7 text-lg font-bold text-black shadow-2xl transition-all duration-500 hover:scale-110 hover:bg-gray-100"
					>
						<span class="relative z-10 flex items-center gap-2">
							Lihat Program Kami
							<span class="transition-transform duration-300 group-hover:translate-x-2">→</span>
						</span>
					</Button>

					<Button
						size="lg"
						class="group relative overflow-hidden border-2 border-red-500 bg-red-500 px-12 py-7 text-lg font-bold text-white shadow-2xl transition-all duration-500 hover:scale-110 hover:border-red-600 hover:bg-red-600"
					>
						<span class="relative z-10 flex items-center gap-2">
							Hubungi Kami
							<span class="transition-transform duration-300 group-hover:translate-x-2">✉️</span>
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

	.mission-card,
	.goal-card,
	.principle-card {
		animation: card-appear 0.8s ease-out forwards;
		opacity: 0;
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
	}
</style>
