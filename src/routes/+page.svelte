<script lang="ts">
	import { onMount } from 'svelte';
	import { Button } from '$lib/components/ui/button/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';

	const heroImages = [
		{
			url: '/images/satumisi1.jpg',
			title: 'Taman Baca Keliling',
			subtitle: 'Membawa literasi ke pelosok desa',
			emoji: '📚'
		},
		{
			url: '/images/satumisi2.jpg',
			title: 'Pelatihan Guru',
			subtitle: 'Workshop metode mengajar',
			emoji: '👨‍🏫'
		},
		{
			url: '/images/satumisi3.jpg',
			title: 'Donasi Buku',
			subtitle: 'Distribusi ke sekolah-sekolah',
			emoji: '📖'
		}
		// {
		// 	url: '/images/kegiatan-4.jpg',
		// 	title: 'Kegiatan Relawan',
		// 	subtitle: 'Bersama membangun literasi',
		// 	emoji: '🤝'
		// }
	];

	const stats = [
		{ number: '10,000+', label: 'Buku Tersebar', icon: '📚' },
		{ number: '50+', label: 'Desa Terjangkau', icon: '🏘️' },
		{ number: '5,000+', label: 'Anak Terbantu', icon: '👶' },
		{ number: '100+', label: 'Relawan Aktif', icon: '🤝' }
	];

	const highlights = [
		{
			title: 'Jadi Mitra',
			description: 'Bergabunglah sebagai mitra untuk kemajuan pendidikan Indonesia',
			icon: '🤝',
			link: '/tentang-kami',
			color: 'from-blue-500 to-blue-600'
		},
		{
			title: 'Donasi',
			description: 'Dukung program literasi dengan donasi dan kontribusi Anda',
			icon: '💰',
			link: '/kontak',
			color: 'from-green-500 to-green-600'
		},
		{
			title: 'Jadi Relawan',
			description: 'Jadilah relawan pengajar untuk membawa perubahan nyata',
			icon: '👨‍🏫',
			link: '/program',
			color: 'from-red-500 to-red-600'
		}
	];

	const recentNews = [
		{
			date: '15 Sep 2024',
			title: 'Peluncuran Program Taman Baca Digital di 10 Desa',
			emoji: '📚',
			category: 'Program Baru',
			excerpt: 'Program baru membawa teknologi digital ke pelosok negeri'
		},
		{
			date: '10 Sep 2024',
			title: 'Workshop Literasi: 50 Guru Terlatih Metode Kreatif',
			emoji: '👨‍🏫',
			category: 'Pelatihan',
			excerpt: 'Guru-guru mendapat pelatihan metode mengajar inovatif'
		},
		{
			date: '5 Sep 2024',
			title: 'Donasi 1000 Buku untuk SD di Pelosok Jawa Barat',
			emoji: '📖',
			category: 'Kegiatan',
			excerpt: 'Ribuan buku baru sampai ke tangan anak-anak yang membutuhkan'
		}
	];

	let currentSlide = 0;

	onMount(() => {
		const interval = setInterval(() => {
			currentSlide = (currentSlide + 1) % heroImages.length;
		}, 5000);

		return () => clearInterval(interval);
	});

	function nextSlide() {
		currentSlide = (currentSlide + 1) % heroImages.length;
	}

	function prevSlide() {
		currentSlide = (currentSlide - 1 + heroImages.length) % heroImages.length;
	}

	function goToSlide(index: number) {
		currentSlide = index;
	}

	function scrollToAbout() {
		document.getElementById('about')?.scrollIntoView({ behavior: 'smooth' });
	}

	function handleDonation() {
		window.location.href = '/kontak';
	}

	function handleWhatsapp() {
		const phone = '6285187268759';
		const message = 'Halo, saya ingin bertanya tentang program Satu Misi.';
		const url = `https://wa.me/${phone}?text=${encodeURIComponent(message)}`;
		window.open(url, '_blank');
	}
</script>

<div class="min-h-screen bg-white">
	<!-- Hero Section - Full Screen Carousel -->
	<section class="relative h-screen overflow-hidden">
		<!-- Image Carousel -->
		<div class="absolute inset-0">
			{#each heroImages as image, i}
				<div
					class="carousel-slide absolute inset-0 transition-opacity duration-1000"
					class:opacity-100={currentSlide === i}
					class:opacity-0={currentSlide !== i}
				>
					<div class="absolute inset-0 bg-gray-900">
						<img src={image.url} alt={image.title} class="h-full w-full object-cover" />
						<div
							class="flex h-full w-full items-center justify-center bg-gradient-to-br from-gray-800 to-gray-900 text-6xl opacity-10 sm:text-8xl md:text-9xl"
						>
							{image.emoji}
						</div>
					</div>
					<div
						class="absolute inset-0 bg-gradient-to-r from-black/90 via-black/70 to-black/50"
					></div>
				</div>
			{/each}
		</div>

		<!-- Content -->
		<div class="relative z-10 flex h-full items-center">
			<div class="container mx-auto px-4">
				<div class="max-w-4xl">
					<div class="hero-badge mb-6 sm:mb-8">
						<Badge
							class="border-2 border-red-500 bg-red-500/20 px-4 py-1.5 text-xs font-bold uppercase tracking-widest text-red-400 backdrop-blur-sm sm:px-6 sm:py-2 sm:text-sm"
						>
							Literasi untuk Indonesia
						</Badge>
					</div>

					<h1
						class="hero-title mb-4 text-5xl font-black leading-none text-white sm:text-6xl md:text-8xl lg:text-9xl"
					>
						Satu Misi
					</h1>

					<div
						class="hero-line mb-6 h-1.5 w-24 rounded-full bg-gradient-to-r from-red-500 via-red-400 to-transparent sm:mb-8 sm:h-2 sm:w-32"
					></div>

					<p
						class="hero-subtitle mb-4 text-2xl font-bold text-red-400 sm:text-3xl md:text-5xl lg:text-6xl"
					>
						Peduli Generasi Negeri
					</p>

					<p
						class="hero-description mb-8 max-w-2xl text-base leading-relaxed text-gray-300 sm:mb-12 sm:text-lg md:text-xl lg:text-2xl"
					>
						Mari ambil bagian untuk kemajuan pendidikan di penjuru Indonesia
					</p>

					<div class="hero-cta flex flex-col gap-3 sm:flex-row sm:gap-4">
						<Button
							size="lg"
							class="group bg-red-500 px-8 py-5 text-base font-bold text-white shadow-2xl transition-all duration-300 hover:scale-105 hover:bg-red-600 sm:px-10 md:px-12 md:py-7 md:text-lg"
							onclick={scrollToAbout}
						>
							<span class="flex items-center gap-3">
								Kenali Kami
								<svg
									class="h-5 w-5 transition-transform group-hover:translate-x-1"
									fill="none"
									stroke="currentColor"
									viewBox="0 0 24 24"
								>
									<path
										stroke-linecap="round"
										stroke-linejoin="round"
										stroke-width="2"
										d="M9 5l7 7-7 7"
									/>
								</svg>
							</span>
						</Button>

						<Button
							size="lg"
							variant="outline"
							class="border-2 border-white bg-white/10 px-8 py-5 text-base font-bold text-white backdrop-blur-sm transition-all duration-300 hover:bg-white hover:text-black sm:px-10 md:px-12 md:py-7 md:text-lg"
							onclick={handleWhatsapp}
						>
							Hubungi Kami
						</Button>
					</div>
				</div>
			</div>
		</div>

		<!-- Navigation -->
		<button
			on:click={prevSlide}
			aria-label="Sebelumnya"
			class="absolute left-2 top-1/2 z-20 -translate-y-1/2 rounded-full bg-white/10 p-3 text-white backdrop-blur-sm transition-all hover:scale-110 hover:bg-white/20 sm:left-4 md:left-8 md:p-4"
		>
			<svg class="h-5 w-5 md:h-6 md:w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
				<path stroke-linecap="round" stroke-linejoin="round" stroke-width="3" d="M15 19l-7-7 7-7" />
			</svg>
		</button>

		<button
			on:click={nextSlide}
			aria-label="Berikutnya"
			class="absolute right-2 top-1/2 z-20 -translate-y-1/2 rounded-full bg-white/10 p-3 text-white backdrop-blur-sm transition-all hover:scale-110 hover:bg-white/20 sm:right-4 md:right-8 md:p-4"
		>
			<svg class="h-5 w-5 md:h-6 md:w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
				<path stroke-linecap="round" stroke-linejoin="round" stroke-width="3" d="M9 5l7 7-7 7" />
			</svg>
		</button>

		<!-- Indicators -->
		<div class="absolute bottom-10 left-1/2 z-20 flex -translate-x-1/2 gap-2 sm:gap-3">
			{#each heroImages as _, i}
				<button
					on:click={() => goToSlide(i)}
					aria-label="pergike"
					class="rounded-full transition-all duration-300"
					class:h-2={currentSlide === i}
					class:w-10={currentSlide === i}
					class:w-2={currentSlide !== i}
					class:bg-red-500={currentSlide === i}
					class:bg-white-30={currentSlide !== i}
					class:sm:h-3={currentSlide === i}
					class:sm:w-12={currentSlide === i}
					class:sm:w-3={currentSlide !== i}
				></button>
			{/each}
		</div>

		<!-- Scroll Hint -->
		<div class="absolute bottom-20 left-1/2 z-20 -translate-x-1/2 animate-bounce">
			<div class="flex flex-col items-center gap-2 text-white/60">
				<span class="text-xs font-medium sm:text-sm">Scroll</span>
				<svg class="h-5 w-5 sm:h-6 sm:w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
					<path
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
						d="M19 14l-7 7m0 0l-7-7m7 7V3"
					/>
				</svg>
			</div>
		</div>
	</section>

	<!-- Stats -->
	<section class="relative bg-gradient-to-b from-gray-50 to-white py-16 sm:py-20 md:py-24">
		<div class="container mx-auto px-4">
			<div class="mx-auto max-w-6xl">
				<div class="grid grid-cols-2 gap-4 sm:gap-6 md:grid-cols-4 md:gap-8">
					{#each stats as stat, i}
						<div class="stat-item group text-center" style="animation-delay: {i * 0.1}s;">
							<div
								class="mb-2 text-4xl transition-transform duration-500 group-hover:rotate-12 group-hover:scale-125 sm:mb-3 sm:text-5xl md:mb-4 md:text-6xl"
							>
								{stat.icon}
							</div>
							<div
								class="mb-1 bg-gradient-to-br from-gray-900 to-gray-600 bg-clip-text text-3xl font-black text-transparent transition-all duration-300 sm:mb-2 sm:text-4xl md:text-5xl lg:text-6xl"
							>
								{stat.number}
							</div>
							<div
								class="text-xs font-bold uppercase tracking-wider text-gray-600 sm:text-sm md:text-base"
							>
								{stat.label}
							</div>
						</div>
					{/each}
				</div>
			</div>
		</div>
	</section>

	<!-- About -->
	<section class="relative overflow-hidden bg-white py-16 sm:py-24 md:py-32" id="about">
		<div class="container mx-auto px-4">
			<div class="mx-auto max-w-5xl">
				<div class="mb-8 text-center sm:mb-12">
					<Badge
						class="mb-4 border-2 border-red-500 bg-red-50 px-4 py-2 text-xs font-bold uppercase tracking-widest text-red-600 sm:mb-6 sm:px-6 sm:py-3 sm:text-sm"
					>
						Tentang Kami
					</Badge>

					<h2 class="mb-4 text-4xl font-black text-gray-900 sm:text-5xl md:text-6xl lg:text-7xl">
						Satu Misi Literasi
					</h2>

					<div
						class="mx-auto mb-8 h-1 w-32 rounded-full bg-gradient-to-r from-red-500 via-red-400 to-transparent sm:mb-12 sm:h-1.5 sm:w-40"
					></div>
				</div>

				<div class="space-y-6 text-center sm:space-y-8">
					<p
						class="fade-in-text text-base leading-relaxed text-gray-700 sm:text-lg md:text-xl lg:text-2xl"
					>
						<strong class="text-red-600">Satu Misi</strong> adalah organisasi nirlaba yang berdedikasi
						untuk meningkatkan literasi di seluruh Indonesia. Kami percaya bahwa setiap anak berhak mendapatkan
						akses pendidikan berkualitas dan bahan bacaan yang memperkaya wawasan.
					</p>

					<div
						class="fade-in-text grid gap-4 text-center sm:gap-6 md:grid-cols-3"
						style="animation-delay: 0.2s;"
					>
						<div
							class="rounded-xl bg-gradient-to-br from-red-50 to-red-100 p-6 sm:rounded-2xl sm:p-8"
						>
							<div class="mb-2 text-4xl sm:mb-3 sm:text-5xl">📚</div>
							<div class="mb-1 text-3xl font-black text-red-600 sm:mb-2 sm:text-4xl">10,000+</div>
							<p class="text-sm font-semibold text-gray-700 sm:text-base">
								Buku tersebar ke 50+ desa
							</p>
						</div>
						<div
							class="rounded-xl bg-gradient-to-br from-blue-50 to-blue-100 p-6 sm:rounded-2xl sm:p-8"
						>
							<div class="mb-2 text-4xl sm:mb-3 sm:text-5xl">👶</div>
							<div class="mb-1 text-3xl font-black text-blue-600 sm:mb-2 sm:text-4xl">5,000+</div>
							<p class="text-sm font-semibold text-gray-700 sm:text-base">
								Anak mendapat akses literasi
							</p>
						</div>
						<div
							class="rounded-xl bg-gradient-to-br from-green-50 to-green-100 p-6 sm:rounded-2xl sm:p-8"
						>
							<div class="mb-2 text-4xl sm:mb-3 sm:text-5xl">🤝</div>
							<div class="mb-1 text-3xl font-black text-green-600 sm:mb-2 sm:text-4xl">100+</div>
							<p class="text-sm font-semibold text-gray-700 sm:text-base">Relawan aktif bergerak</p>
						</div>
					</div>

					<div class="fade-in-text pt-6 sm:pt-8" style="animation-delay: 0.4s;">
						<Button
							size="lg"
							class="bg-red-500 px-8 py-5 text-base font-bold text-white shadow-xl transition-all duration-300 hover:scale-105 hover:bg-red-600 sm:px-10 sm:py-6 sm:text-lg"
							onclick={() => (window.location.href = '/tentang')}
						>
							Selengkapnya Tentang Kami
						</Button>
					</div>
				</div>
			</div>
		</div>
	</section>

	<!-- Highlights -->
	<section class="relative bg-gradient-to-b from-gray-50 to-white py-16 sm:py-24 md:py-32">
		<div class="container mx-auto px-4">
			<div class="mx-auto max-w-6xl">
				<div class="mb-12 text-center sm:mb-16">
					<h2
						class="mb-3 text-3xl font-black text-gray-900 sm:mb-4 sm:text-4xl md:text-5xl lg:text-6xl"
					>
						Cara Anda Berkontribusi
					</h2>
					<p class="text-base text-gray-600 sm:text-lg md:text-xl">
						Pilih cara terbaik untuk berkontribusi
					</p>
				</div>

				<div class="grid gap-6 sm:gap-8 md:grid-cols-3">
					{#each highlights as highlight, i}
						<a
							href={highlight.link}
							class="highlight-card group relative overflow-hidden rounded-2xl bg-white p-6 shadow-xl transition-all duration-500 hover:-translate-y-3 hover:shadow-2xl sm:rounded-3xl sm:p-8 md:p-10"
							style="animation-delay: {i * 0.15}s;"
						>
							<div
								class="absolute inset-0 bg-gradient-to-br {highlight.color} opacity-0 transition-opacity duration-500 group-hover:opacity-10"
							></div>

							<div class="relative">
								<div
									class="mb-4 text-5xl transition-all duration-500 group-hover:rotate-6 group-hover:scale-110 sm:mb-6 sm:text-6xl md:text-7xl"
								>
									{highlight.icon}
								</div>

								<h3 class="mb-3 text-2xl font-black text-gray-900 sm:mb-4 sm:text-3xl">
									{highlight.title}
								</h3>

								<div
									class="mb-4 h-1 w-16 rounded-full bg-gradient-to-r {highlight.color} transition-all duration-500 group-hover:w-full sm:mb-6 sm:h-1.5 sm:w-20"
								></div>

								<p class="mb-4 text-base leading-relaxed text-gray-600 sm:mb-6 sm:text-lg">
									{highlight.description}
								</p>

								<div
									class="flex items-center gap-2 text-sm font-bold text-red-600 transition-transform duration-300 group-hover:translate-x-2 sm:text-base"
								>
									Pelajari Lebih Lanjut
									<svg
										class="h-4 w-4 sm:h-5 sm:w-5"
										fill="none"
										stroke="currentColor"
										viewBox="0 0 24 24"
									>
										<path
											stroke-linecap="round"
											stroke-linejoin="round"
											stroke-width="2"
											d="M9 5l7 7-7 7"
										/>
									</svg>
								</div>
							</div>
						</a>
					{/each}
				</div>
			</div>
		</div>
	</section>

	<!-- News -->
	<section class="relative bg-white py-16 sm:py-24 md:py-32">
		<div class="container mx-auto px-4">
			<div class="mx-auto max-w-6xl">
				<div class="mb-12 text-center sm:mb-16">
					<Badge
						class="mb-4 bg-gray-900 px-4 py-2 text-xs font-bold uppercase tracking-widest text-white sm:mb-6 sm:px-6 sm:py-3 sm:text-sm"
					>
						Berita & Kegiatan
					</Badge>

					<h2
						class="mb-3 text-3xl font-black text-gray-900 sm:mb-4 sm:text-4xl md:text-5xl lg:text-6xl"
					>
						Update Terbaru
					</h2>
					<p class="text-base text-gray-600 sm:text-lg md:text-xl">
						Lihat apa yang sedang kami kerjakan
					</p>
				</div>

				<div class="grid gap-6 sm:gap-8 md:grid-cols-3">
					{#each recentNews as news, i}
						<Card
							class="news-card group overflow-hidden rounded-2xl border-2 border-gray-200 bg-white transition-all duration-500 hover:-translate-y-2 hover:border-red-500 hover:shadow-2xl sm:rounded-3xl"
							style="animation-delay: {i * 0.15}s;"
						>
							<div
								class="relative h-48 overflow-hidden bg-gradient-to-br from-gray-800 to-gray-900 sm:h-56"
							>
								<div
									class="flex h-full w-full items-center justify-center text-6xl opacity-20 transition-all duration-500 group-hover:scale-125 sm:text-7xl md:text-8xl"
								>
									{news.emoji}
								</div>
								<div class="absolute left-4 top-4 sm:left-6 sm:top-6">
									<Badge class="bg-red-500 text-xs font-bold text-white sm:text-sm">
										{news.category}
									</Badge>
								</div>
							</div>

							<CardContent class="p-6 sm:p-8">
								<div
									class="mb-2 text-xs font-bold uppercase tracking-wider text-gray-500 sm:mb-3 sm:text-sm"
								>
									{news.date}
								</div>
								<CardTitle
									class="mb-3 text-xl font-black leading-tight text-gray-900 sm:mb-4 sm:text-2xl"
								>
									{news.title}
								</CardTitle>
								<p class="mb-4 text-sm text-gray-600 sm:mb-6 sm:text-base">{news.excerpt}</p>
								<div
									class="flex items-center gap-2 text-sm font-bold text-red-600 transition-transform duration-300 group-hover:translate-x-2 sm:text-base"
								>
									Baca Selengkapnya
									<svg class="h-4 w-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
										<path
											stroke-linecap="round"
											stroke-linejoin="round"
											stroke-width="2"
											d="M9 5l7 7-7 7"
										/>
									</svg>
								</div>
							</CardContent>
						</Card>
					{/each}
				</div>

				<div class="mt-10 text-center sm:mt-12">
					<Button
						size="lg"
						variant="outline"
						class="border-2 border-gray-900 bg-white px-8 py-5 text-base font-bold text-gray-900 transition-all duration-300 hover:bg-gray-900 hover:text-white sm:px-12 sm:py-6 sm:text-lg"
					>
						Lihat Semua Berita
					</Button>
				</div>
			</div>
		</div>
	</section>

	<!-- CTA -->
	<section
		class="relative overflow-hidden bg-gradient-to-br from-red-600 via-red-500 to-red-700 py-16 sm:py-24 md:py-32"
	>
		<div class="absolute inset-0 opacity-10">
			<div class="animate-float absolute left-1/4 top-20 text-6xl sm:text-7xl md:text-8xl">📚</div>
			<div class="animate-float-delayed absolute right-1/4 top-32 text-5xl sm:text-6xl md:text-7xl">
				✏️
			</div>
			<div class="animate-float-slow absolute bottom-20 left-1/3 text-7xl sm:text-8xl md:text-9xl">
				📖
			</div>
		</div>

		<div class="container relative mx-auto px-4">
			<div class="mx-auto max-w-4xl text-center">
				<h2 class="mb-6 text-4xl font-black text-white sm:mb-8 sm:text-5xl md:text-6xl lg:text-7xl">
					Mari Bergabung Bersama Kami
				</h2>

				<div class="mx-auto mb-8 h-1.5 w-32 rounded-full bg-white/30 sm:mb-10 sm:h-2 sm:w-40"></div>

				<p class="mb-10 text-lg leading-relaxed text-white/90 sm:mb-14 sm:text-xl md:text-2xl">
					Setiap kontribusi Anda membawa perubahan nyata untuk masa depan pendidikan Indonesia
				</p>

				<div class="flex flex-col gap-4 sm:flex-row sm:justify-center sm:gap-5">
					<Button
						size="lg"
						class="bg-white px-10 py-6 text-lg font-bold text-red-600 shadow-2xl transition-all duration-300 hover:scale-105 hover:bg-gray-100 sm:px-12 sm:py-8 sm:text-xl"
						onclick={handleDonation}
					>
						Donasi Sekarang
					</Button>

					<Button
						size="lg"
						variant="outline"
						class="border-4 border-white bg-transparent px-10 py-6 text-lg font-bold text-white transition-all duration-300 hover:scale-105 hover:bg-white hover:text-red-600 sm:px-12 sm:py-8 sm:text-xl"
						onclick={handleWhatsapp}
					>
						Hubungi Kami
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

	.hero-badge {
		animation: fade-in-up 1s ease-out 0.1s forwards;
		opacity: 0;
	}
	.hero-title {
		animation: fade-in-up 1s ease-out 0.3s forwards;
		opacity: 0;
	}
	.hero-line {
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
	.hero-cta {
		animation: fade-in-up 1s ease-out 1.1s forwards;
		opacity: 0;
	}

	.stat-item {
		animation: fade-in-up 0.8s ease-out forwards;
		opacity: 0;
	}
	.fade-in-text {
		animation: fade-in-up 1s ease-out forwards;
		opacity: 0;
	}
	.highlight-card {
		animation: fade-in-up 0.8s ease-out forwards;
		opacity: 0;
	}
	.news-card {
		animation: fade-in-up 0.8s ease-out forwards;
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

	.carousel-slide {
		z-index: 0;
	}
	.carousel-slide.opacity-100 {
		z-index: 1;
	}

	html {
		scroll-behavior: smooth;
	}
</style>
