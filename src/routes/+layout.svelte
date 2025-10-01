<script>
	import '../app.css';
	import { page } from '$app/stores';
	import { Button } from '$lib/components/ui/button/index.js';
	import { Sheet, SheetContent, SheetTrigger } from '$lib/components/ui/sheet/index.js';
	import { Menu, Instagram, Linkedin, MessageCircle } from '@lucide/svelte';

	let mobileMenuOpen = false;

	const navItems = [
		{ href: '/', label: 'Beranda' },
		{ href: '/tentang', label: 'Tentang Kami' },
		{ href: '/visi-misi', label: 'Visi & Misi' },
		{ href: '/program', label: 'Program' },
		{ href: '/kontak', label: 'Kontak' }
	];
</script>

<div class="flex min-h-screen flex-col">
	<!-- Header - Enhanced with Logo Theme -->
	<header
		class="bg-white/98 sticky top-0 z-50 border-b-2 border-gray-200 shadow-sm backdrop-blur-md"
	>
		<nav class="container mx-auto px-4 py-4">
			<div class="flex items-center justify-between">
				<!-- Logo - Circular with Book Icon -->
				<a href="/" class="group flex items-center space-x-4">
					<div class="relative">
						<div
							class="flex h-14 w-14 items-center justify-center rounded-full border-2 border-gray-800 bg-gradient-to-br from-gray-700 to-gray-900 transition-all duration-300 group-hover:border-red-500 group-hover:shadow-lg group-hover:shadow-red-500/20"
						>
							<img
								src="/images/logo.png"
								alt="Logo Satu Misi"
								class="w-full rounded-full object-contain"
							/>
						</div>
						<div
							class="absolute -bottom-1 -right-1 h-4 w-4 rounded-full border-2 border-white bg-red-500"
						></div>
					</div>
					<div>
						<h1
							class="text-2xl font-black tracking-tight text-gray-900 transition-colors group-hover:text-red-600"
						>
							Satu Misi
						</h1>
						<p class="text-xs font-semibold text-gray-600">Peduli Generasi Negeri</p>
					</div>
				</a>

				<!-- Desktop Navigation -->
				<ul class="hidden items-center space-x-1 md:flex">
					{#each navItems as item}
						<li>
							<a
								href={item.href}
								class="relative px-4 py-2 text-sm font-semibold transition-all duration-300 hover:text-red-600"
								class:text-red-600={$page.url.pathname === item.href}
								class:bg-gray-100={$page.url.pathname === item.href}
								class:text-gray-700={$page.url.pathname !== item.href}
							>
								{item.label}
								{#if $page.url.pathname === item.href}
									<span class="absolute bottom-0 left-0 right-0 h-1 rounded-t-full bg-red-500"
									></span>
								{/if}
							</a>
						</li>
					{/each}
					<li class="ml-4">
						<Button
							size="sm"
							class="relative overflow-hidden bg-red-500 px-6 py-2 font-bold text-white shadow-lg transition-all duration-300 hover:scale-105 hover:bg-red-600 hover:shadow-xl"
						>
							<span class="relative z-10">Donasi</span>
							<div
								class="absolute inset-0 bg-gradient-to-r from-red-600 to-red-700 opacity-0 transition-opacity hover:opacity-100"
							></div>
						</Button>
					</li>
				</ul>

				<!-- Mobile Menu Button -->
				<Sheet bind:open={mobileMenuOpen}>
					<SheetTrigger>
						<Button variant="ghost" size="icon" class="hover:bg-gray-100 md:hidden">
							<Menu class="h-6 w-6 text-gray-900" />
						</Button>
					</SheetTrigger>
					<SheetContent side="right" class="w-[300px] bg-white sm:w-[400px]">
						<div class="mb-8 flex items-center space-x-3">
							<div
								class="flex h-12 w-12 items-center justify-center rounded-full border-2 border-gray-800 bg-gradient-to-br from-gray-700 to-gray-900 text-xl"
							>
								📖
							</div>
							<div>
								<h3 class="text-xl font-black text-gray-900">Satu Misi</h3>
								<p class="text-xs font-semibold text-gray-600">Peduli Generasi Negeri</p>
							</div>
						</div>

						<nav class="flex flex-col gap-2">
							{#each navItems as item}
								<a
									href={item.href}
									class={`px-4 py-3 text-base font-semibold transition-all duration-300 ${
										$page.url.pathname === item.href
											? 'bg-red-500 text-white'
											: 'text-gray-700 hover:bg-gray-100 hover:text-red-600'
									}`}
									on:click={() => (mobileMenuOpen = false)}
								>
									{item.label}
								</a>
							{/each}
							<Button class="mt-6 bg-red-500 font-bold text-white shadow-lg hover:bg-red-600">
								Donasi Sekarang
							</Button>
						</nav>
					</SheetContent>
				</Sheet>
			</div>
		</nav>
	</header>

	<!-- Main Content -->
	<main class="flex-grow">
		<slot />
	</main>

	<!-- Footer - Enhanced with Logo Theme -->
	<footer
		class="relative overflow-hidden bg-gradient-to-br from-gray-900 via-gray-800 to-black text-white"
	>
		<!-- Decorative Wave -->
		<div class="absolute top-0 w-full opacity-10">
			<svg viewBox="0 0 1440 120" xmlns="http://www.w3.org/2000/svg">
				<path
					fill="#ffffff"
					fill-opacity="0.3"
					d="M0,64L48,69.3C96,75,192,85,288,80C384,75,480,53,576,48C672,43,768,53,864,64C960,75,1056,85,1152,80C1248,75,1344,53,1392,42.7L1440,32L1440,0L1392,0C1344,0,1248,0,1152,0C1056,0,960,0,864,0C768,0,672,0,576,0C480,0,384,0,288,0C192,0,96,0,48,0L0,0Z"
				></path>
			</svg>
		</div>

		<div class="container relative mx-auto px-4 py-16">
			<div class="grid grid-cols-1 gap-12 md:grid-cols-4">
				<!-- Brand Section -->
				<div class="md:col-span-2">
					<div class="mb-6 flex items-center space-x-4">
						<div
							class="border-3 flex h-16 w-16 items-center justify-center rounded-full border-white/30 bg-gradient-to-br from-gray-700 to-gray-900 text-3xl shadow-xl"
						>
							📖
						</div>
						<div>
							<h3 class="text-3xl font-black text-white">Satu Misi</h3>
							<p class="text-sm font-semibold text-gray-400">Peduli Generasi Negeri</p>
						</div>
					</div>
					<p class="mb-8 max-w-md leading-relaxed text-gray-300">
						Membangun literasi untuk Indonesia yang lebih baik. Bersama menciptakan generasi yang
						cerdas dan berdaya saing tinggi.
					</p>

					<div class="flex gap-3">
						<!-- Instagram -->
						<a
							href="https://www.instagram.com/satumisi.official"
							target="_blank"
							rel="noopener noreferrer"
							aria-label="Instagram"
							class="group flex h-12 w-12 items-center justify-center rounded-full border-2 border-white/20 bg-white/5 backdrop-blur-sm transition-all duration-300 hover:scale-110 hover:border-red-500 hover:bg-red-500"
						>
							<Instagram class="h-6 w-6 text-white group-hover:text-white" />
						</a>

						<!-- LinkedIn -->
						<!-- <a
							href="https://www.linkedin.com/company/satumisi"
							target="_blank"
							rel="noopener noreferrer"
							aria-label="LinkedIn"
							class="group flex h-12 w-12 items-center justify-center rounded-full border-2 border-white/20 bg-white/5 backdrop-blur-sm transition-all duration-300 hover:scale-110 hover:border-red-500 hover:bg-red-500"
						>
							<Linkedin class="h-6 w-6 text-white group-hover:text-white" />
						</a> -->

						<!-- WhatsApp -->
						<a
							href="https://wa.me/6285187268759"
							target="_blank"
							rel="noopener noreferrer"
							aria-label="WhatsApp"
							class="group flex h-12 w-12 items-center justify-center rounded-full border-2 border-white/20 bg-white/5 backdrop-blur-sm transition-all duration-300 hover:scale-110 hover:border-red-500 hover:bg-red-500"
						>
							<MessageCircle class="h-6 w-6 text-white group-hover:text-white" />
						</a>
					</div>
				</div>

				<!-- Quick Links -->
				<div>
					<h4 class="mb-6 text-lg font-black text-white">Tautan Cepat</h4>
					<ul class="space-y-3">
						{#each navItems as item}
							<li>
								<a
									href={item.href}
									class="group flex items-center gap-2 text-sm text-gray-400 transition-all duration-300 hover:translate-x-1 hover:text-red-500"
								>
									<span class="text-red-500 transition-transform group-hover:translate-x-1">→</span>
									{item.label}
								</a>
							</li>
						{/each}
					</ul>
				</div>

				<!-- Contact Info -->
				<div>
					<h4 class="mb-6 text-lg font-black text-white">Hubungi Kami</h4>
					<ul class="space-y-4 text-sm">
						<li class="group flex items-start gap-3">
							<span
								class="flex h-8 w-8 items-center justify-center rounded-full bg-white/10 text-base transition-colors group-hover:bg-red-500"
								>📧</span
							>
							<div>
								<p class="mb-1 text-xs font-semibold text-gray-500">Email</p>
								<a
									href="mailto:Bukumembaca9@gmail.com"
									class="text-gray-300 transition-colors hover:text-red-500"
								>
									Bukumembaca9@gmail.com
								</a>
							</div>
						</li>
						<li class="group flex items-start gap-3">
							<span
								class="flex h-8 w-8 items-center justify-center rounded-full bg-white/10 text-base transition-colors group-hover:bg-red-500"
								>📞</span
							>
							<div>
								<p class="mb-1 text-xs font-semibold text-gray-500">Telepon</p>
								<a
									href="tel:+6285187268759"
									class="text-gray-300 transition-colors hover:text-red-500"
								>
									+62 851-8726-8759
								</a>
							</div>
						</li>
						<li class="group flex items-start gap-3">
							<span
								class="flex h-8 w-8 items-center justify-center rounded-full bg-white/10 text-base transition-colors group-hover:bg-red-500"
								>📍</span
							>
							<div>
								<p class="mb-1 text-xs font-semibold text-gray-500">Alamat</p>
								<p class="text-gray-300">
									Cigondewah Hilir, Kec. Margaasih, Kabupaten Bandung, Jawa Barat 40214
								</p>
							</div>
						</li>
					</ul>
				</div>
			</div>

			<!-- Footer Bottom -->
			<div class="mt-12 border-t-2 border-white/10 pt-8">
				<div class="flex flex-col items-center justify-between gap-4 md:flex-row">
					<p class="text-sm font-semibold text-gray-400">
						© 2025 Satu Misi. Semua hak dilindungi.
					</p>
					<div class="flex gap-6 text-sm font-semibold text-gray-400">
						<a href="/kebijakan-privasi" class="transition-colors hover:text-red-500"
							>Kebijakan Privasi</a
						>
						<span class="text-gray-600">•</span>
						<a href="/syarat-ketentuan" class="transition-colors hover:text-red-500"
							>Syarat & Ketentuan</a
						>
					</div>
				</div>
			</div>
		</div>

		<!-- Decorative Red Accent Line -->
		<div
			class="absolute bottom-0 left-0 right-0 h-1 bg-gradient-to-r from-transparent via-red-500 to-transparent"
		></div>
	</footer>
</div>

<style>
	:global(body) {
		margin: 0;
		font-family:
			-apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, sans-serif;
	}

	/* Smooth scrollbar */
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
</style>
