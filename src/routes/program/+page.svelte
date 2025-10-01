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
	import { Check } from '@lucide/svelte';

	const programs = [
		{
			title: 'Taman Baca Keliling',
			description:
				'Program unggulan kami yang membawa perpustakaan mini ke desa-desa terpencil menggunakan mobil khusus yang dilengkapi dengan ribuan buku berkualitas.',
			icon: '🚐',
			benefits: [
				'Menjangkau 50+ desa di seluruh Indonesia',
				'Koleksi 3,000+ buku per unit',
				'Kunjungan rutin setiap 2 minggu',
				'Kegiatan membaca bersama dan mendongeng'
			]
		},
		{
			title: 'Pelatihan Guru & Relawan',
			description:
				'Program pemberdayaan pendidik dengan metode pengajaran literasi yang kreatif, inovatif, dan menyenangkan untuk meningkatkan minat baca siswa.',
			icon: '👨‍🏫',
			benefits: [
				'Workshop metode pembelajaran kreatif',
				'Sertifikasi literasi nasional',
				'Mentoring berkelanjutan',
				'Jaringan komunitas guru literasi'
			]
		},
		{
			title: 'Donasi & Distribusi Buku',
			description:
				'Mengumpulkan buku-buku berkualitas dari donatur dan mendistribusikannya ke sekolah-sekolah dan taman baca di daerah yang membutuhkan.',
			icon: '📚',
			benefits: [
				'10,000+ buku terdistribusi per tahun',
				'Kurasi buku sesuai usia & kebutuhan',
				'Kerjasama dengan penerbit mayor',
				'Transparansi distribusi penuh'
			]
		},
		{
			title: 'Literasi Digital',
			description:
				'Memperkenalkan dan mengajarkan keterampilan literasi digital, penggunaan teknologi untuk pembelajaran, dan literasi media kepada anak-anak dan remaja.',
			icon: '💻',
			benefits: [
				'Pelatihan penggunaan perangkat digital',
				'Edukasi keamanan internet',
				'Literasi media sosial',
				'Akses ke perpustakaan digital'
			]
		},
		{
			title: 'Pojok Baca Sekolah',
			description:
				'Membangun dan mengelola pojok baca di sekolah-sekolah sebagai ruang nyaman untuk siswa membaca dan mengeksplorasi dunia literasi.',
			icon: '🏫',
			benefits: [
				'Desain ruang ramah anak',
				'Koleksi buku yang terus diperbarui',
				'Program reading challenge',
				'Pendampingan pengelolaan'
			]
		},
		{
			title: 'Festival Literasi',
			description:
				'Menyelenggarakan festival dan acara literasi yang meriah untuk meningkatkan kesadaran dan minat masyarakat terhadap budaya membaca.',
			icon: '🎉',
			benefits: [
				'Acara tahunan di berbagai kota',
				'Lomba menulis & bercerita',
				'Talkshow dengan penulis terkenal',
				'Bazar buku murah'
			]
		}
	];

	const impacts = [
		{ number: '50+', label: 'Desa Terjangkau', icon: '🏘️' },
		{ number: '10K+', label: 'Buku Didistribusikan', icon: '📚' },
		{ number: '5K+', label: 'Anak Terbantu', icon: '👶' },
		{ number: '100+', label: 'Relawan Aktif', icon: '🤝' }
	];
</script>

<svelte:head>
	<title>Program Kami - Satu Misi</title>
	<meta
		name="description"
		content="Berbagai inisiatif untuk meningkatkan literasi dan memberdayakan generasi Indonesia"
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
			<div class="animate-float absolute left-1/4 top-20 text-6xl opacity-5">📚</div>
			<div class="animate-float-delayed absolute right-1/4 top-40 text-5xl opacity-5">🚐</div>
			<div class="animate-float-slow absolute bottom-40 left-1/3 text-7xl opacity-5">💻</div>
		</div>

		<div class="container relative z-10 mx-auto px-4 text-center">
			<Badge
				variant="outline"
				class="hero-badge mb-8 border-white/30 bg-white/10 px-6 py-2 text-xs font-bold tracking-widest text-white/90 backdrop-blur-sm"
			>
				INISIATIF KAMI
			</Badge>

			<h1 class="hero-title mb-8 text-6xl font-black tracking-tight text-white md:text-8xl">
				Program Kami
			</h1>

			<div
				class="shadow-red hero-subtitle mx-auto mb-10 h-1 w-40 bg-gradient-to-r from-transparent via-red-500 to-transparent"
			></div>

			<p
				class="hero-description mx-auto max-w-3xl text-2xl font-light leading-relaxed text-gray-300 md:text-3xl"
			>
				Berbagai inisiatif untuk meningkatkan literasi dan memberdayakan generasi Indonesia
			</p>
		</div>
	</section>

	<!-- Programs Section - Enhanced Layout -->
	<section class="relative overflow-hidden bg-white py-32">
		<div class="absolute inset-0 bg-gradient-to-b from-gray-50 to-white"></div>

		<!-- Decorative Elements -->
		<div class="absolute right-0 top-40 h-96 w-96 rounded-full bg-red-500/5 blur-3xl"></div>
		<div class="absolute bottom-40 left-0 h-96 w-96 rounded-full bg-gray-900/5 blur-3xl"></div>

		<div class="container relative mx-auto px-4">
			<div class="mx-auto max-w-7xl space-y-16">
				{#each programs as program, index}
					<Card
						class="program-card group overflow-hidden rounded-3xl border-2 border-gray-200 transition-all duration-700 hover:border-red-500 hover:shadow-2xl"
						style="animation-delay: {index * 0.15}s;"
					>
						<div class="md:flex">
							<!-- Icon & Number Section -->
							<div
								class="relative flex flex-col items-center justify-center bg-gradient-to-br from-gray-900 via-gray-800 to-black p-12 text-white transition-all duration-700 group-hover:from-red-600 group-hover:to-red-700 md:w-1/3"
							>
								<!-- Background Pattern -->
								<div class="absolute inset-0 opacity-5">
									<div
										class="absolute right-0 top-0 h-32 w-32 rounded-full bg-white blur-2xl"
									></div>
									<div
										class="absolute bottom-0 left-0 h-32 w-32 rounded-full bg-white blur-2xl"
									></div>
								</div>

								<div class="relative">
									<div
										class="mb-6 text-8xl transition-all duration-700 group-hover:rotate-12 group-hover:scale-125"
									>
										{program.icon}
									</div>
									<div
										class="absolute -inset-8 -z-10 rounded-full bg-white/0 blur-2xl transition-all duration-700 group-hover:bg-white/20"
									></div>
								</div>

								<div
									class="relative rounded-lg border-2 border-white/20 bg-white/10 px-6 py-3 backdrop-blur-sm transition-all duration-500 group-hover:scale-110 group-hover:border-white/40"
								>
									<div class="text-5xl font-black">0{index + 1}</div>
								</div>
							</div>

							<!-- Content Section -->
							<div class="relative p-8 md:w-2/3 md:p-12">
								<!-- Hover Glow Effect -->
								<div
									class="absolute right-0 top-0 h-64 w-64 -translate-y-32 translate-x-32 rounded-full bg-red-500/0 blur-3xl transition-all duration-700 group-hover:bg-red-500/10"
								></div>

								<CardHeader class="relative mb-6 p-0">
									<CardTitle class="mb-4 text-3xl font-black text-gray-900 md:text-4xl">
										{program.title}
									</CardTitle>
									<div
										class="mb-4 h-1 w-16 rounded-full bg-gray-300 transition-all duration-500 group-hover:w-32 group-hover:bg-red-500"
									></div>
									<CardDescription class="text-lg leading-relaxed text-gray-700">
										{program.description}
									</CardDescription>
								</CardHeader>

								<CardContent class="relative p-0">
									<h3 class="mb-4 text-lg font-bold text-gray-900">Manfaat Program:</h3>
									<ul class="space-y-3">
										{#each program.benefits as benefit, i}
											<li
												class="group/item flex items-start gap-3 transition-all duration-300 hover:translate-x-2"
											>
												<div
													class="mt-0.5 flex h-6 w-6 flex-shrink-0 items-center justify-center rounded-full bg-gradient-to-br from-gray-800 to-black shadow-lg transition-all duration-300 group-hover/item:scale-110 group-hover/item:from-red-600 group-hover/item:to-red-700"
												>
													<Check class="h-3.5 w-3.5 text-white" />
												</div>
												<span class="leading-relaxed text-gray-700">{benefit}</span>
											</li>
										{/each}
									</ul>
								</CardContent>
							</div>
						</div>

						<!-- Bottom Accent Line -->
						<div
							class="h-2 bg-gradient-to-r from-transparent via-red-500 to-transparent opacity-0 transition-opacity duration-700 group-hover:opacity-100"
						></div>
					</Card>
				{/each}
			</div>
		</div>
	</section>

	<!-- Impact Section - Matching Home Page Stats -->
	<section class="relative overflow-hidden bg-gradient-to-b from-white to-gray-50 py-32">
		<div class="container relative mx-auto px-4">
			<div class="mx-auto max-w-5xl text-center">
				<div class="mb-12 text-center">
					<Badge
						class="bg-gradient-to-r from-gray-800 to-black px-5 py-2 text-xs font-bold tracking-widest text-white shadow-lg"
					>
						DAMPAK KAMI
					</Badge>
				</div>

				<h2 class="mb-12 text-6xl font-black tracking-tight text-gray-900 md:text-7xl">
					Dampak Program Kami
				</h2>

				<div
					class="shadow-red mx-auto mb-12 h-1 w-40 rounded-full bg-gradient-to-r from-transparent via-red-500 to-transparent"
				></div>

				<p class="mx-auto mb-16 max-w-3xl text-xl leading-relaxed text-gray-700">
					Melalui berbagai program yang kami jalankan, kami telah memberikan dampak nyata bagi
					ribuan anak Indonesia
				</p>

				<div class="grid grid-cols-2 gap-10 md:grid-cols-4 md:gap-16">
					{#each impacts as impact, i}
						<div
							class="stat-item group cursor-default text-center"
							style="animation-delay: {i * 0.15}s;"
						>
							<div class="relative mb-6">
								<div
									class="absolute inset-0 -z-10 scale-0 rounded-3xl bg-red-500/10 blur-2xl transition-transform duration-700 group-hover:scale-150"
								></div>

								<div class="mb-4 text-7xl transition-transform duration-500 group-hover:scale-125">
									{impact.icon}
								</div>

								<div
									class="stat-number mb-2 text-6xl font-black text-gray-900 transition-colors duration-300 group-hover:text-red-600 md:text-7xl"
								>
									{impact.number}
								</div>
							</div>

							<div class="text-sm font-bold uppercase tracking-wider text-gray-600 md:text-base">
								{impact.label}
							</div>

							<div
								class="mx-auto mt-5 h-1 w-16 rounded-full bg-red-500 opacity-0 transition-all duration-500 group-hover:w-full group-hover:opacity-100"
							></div>
						</div>
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
					MARI BERKONTRIBUSI
				</Badge>

				<h2 class="mb-12 text-5xl font-black tracking-tight text-white md:text-7xl">
					Ingin Mendukung Program Kami?
				</h2>

				<div
					class="shadow-red mx-auto mb-12 h-1 w-40 rounded-full bg-gradient-to-r from-transparent via-red-500 to-transparent"
				></div>

				<p class="mx-auto mb-16 max-w-3xl text-2xl font-light leading-relaxed text-gray-300">
					Ada banyak cara untuk berkontribusi dalam misi kami. Mari bersama membangun Indonesia yang
					lebih literat.
				</p>

				<div class="flex flex-col justify-center gap-6 sm:flex-row">
					<Button
						size="lg"
						class="group relative overflow-hidden border-2 border-white bg-white px-12 py-7 text-lg font-bold text-black shadow-2xl transition-all duration-500 hover:scale-110 hover:bg-gray-100"
					>
						<span class="relative z-10 flex items-center gap-2">
							Donasi Sekarang
							<span class="transition-transform duration-300 group-hover:scale-125">❤️</span>
						</span>
					</Button>

					<Button
						size="lg"
						class="group relative overflow-hidden border-2 border-red-500 bg-red-500 px-12 py-7 text-lg font-bold text-white shadow-2xl transition-all duration-500 hover:scale-110 hover:border-red-600 hover:bg-red-600"
					>
						<span class="relative z-10 flex items-center gap-2">
							Jadi Relawan
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

	@keyframes stat-appear {
		from {
			opacity: 0;
			transform: translateY(40px) scale(0.8);
		}
		to {
			opacity: 1;
			transform: translateY(0) scale(1);
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

	.program-card {
		animation: card-appear 0.8s ease-out forwards;
		opacity: 0;
	}

	.stat-item {
		animation: stat-appear 0.8s ease-out forwards;
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
