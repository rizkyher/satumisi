<script lang="ts">
	import { Button } from '$lib/components/ui/button/index.js';
	import { Card, CardContent, CardHeader, CardTitle } from '$lib/components/ui/card/index.js';
	import { Badge } from '$lib/components/ui/badge/index.js';
	import { Input } from '$lib/components/ui/input/index.js';
	import { Label } from '$lib/components/ui/label/index.js';
	import { Textarea } from '$lib/components/ui/textarea/index.js';
	import {
		Select,
		SelectContent,
		SelectItem,
		SelectTrigger
	} from '$lib/components/ui/select/index.js';
	import { CheckCircle2, Instagram, Linkedin } from '@lucide/svelte';

	const subjects = [
		'Informasi Umum',
		'Donasi',
		'Menjadi Relawan',
		'Kerjasama',
		'Media & Publikasi',
		'Lainnya'
	];

	const contacts = [
		{
			icon: '📧',
			title: 'Email',
			value: 'Bukumembaca9@gmail.com',
			link: 'mailto:Bukumembaca9@gmail.com',
			gradient: 'from-blue-500 to-cyan-500'
		},
		{
			icon: '📱',
			title: 'Telepon',
			value: '+62 851-8726-8759',
			link: 'tel:+6285187268759',
			gradient: 'from-purple-500 to-pink-500'
		},
		{
			icon: '💬',
			title: 'WhatsApp',
			value: '+62 851-8726-8759',
			link: 'https://wa.me/6285187268759',
			gradient: 'from-green-500 to-emerald-500'
		},
		{
			icon: '📍',
			title: 'Alamat',
			value: 'Cigondewah Hilir, Kec. Margaasih, Kabupaten Bandung, Jawa Barat 40214',
			link: '#',
			gradient: 'from-orange-500 to-red-500'
		}
	];

	const socialMedia = [
		{
			name: 'Instagram',
			icon: Instagram,
			link: 'https://www.instagram.com/satumisi.official?igsh=MW1mN2lua3BwbXBkdQ==',
			handle: '@satumisi.official'
		},
		{ name: 'Linkedin', icon: Linkedin, link: '#', handle: 'Satu Misi' }
	];

	const officeHours = [
		{ day: 'Senin - Jumat', time: '09:00 - 17:00', open: true },
		{ day: 'Sabtu', time: '09:00 - 14:00', open: true },
		{ day: 'Minggu & Libur', time: 'Tutup', open: false }
	];

	let submitted = false;

	let formData = {
		name: '',
		email: '',
		phone: '',
		subject: 'Informasi Umum',
		message: ''
	};

	const phoneNumber = '6285187268759'; // format internasional tanpa +

	function handleSubmit(e: SubmitEvent) {
		e.preventDefault();
		submitted = true;

		// bikin pesan WhatsApp
		const text = `Halo, saya ${formData.name}.\n\nEmail: ${formData.email}\nTelepon: ${formData.phone}\n\nPerihal: ${formData.subject}\nPesan:\n${formData.message}`;

		// encode pesan biar aman di URL
		const encodedText = encodeURIComponent(text);

		// redirect ke WhatsApp
		window.open(`https://wa.me/${phoneNumber}?text=${encodedText}`, '_blank');

		// reset form setelah 3 detik
		setTimeout(() => {
			submitted = false;
			formData = {
				name: '',
				email: '',
				phone: '',
				subject: 'Informasi Umum',
				message: ''
			};
		}, 3000);
	}
</script>

<svelte:head>
	<title>Hubungi Kami - Satu Misi</title>
</svelte:head>

<!-- Hero Section - Logo Theme -->
<section
	class="relative overflow-hidden bg-gradient-to-br from-gray-900 via-gray-800 to-black py-32"
>
	<!-- Floating Book Icons -->
	<div class="absolute inset-0">
		<div class="animate-float absolute left-1/4 top-20 text-6xl opacity-5">📖</div>
		<div class="animate-float-delayed absolute right-1/4 top-40 text-5xl opacity-5">📚</div>
		<div class="animate-float-slow absolute bottom-20 left-1/3 text-7xl opacity-5">✉️</div>
	</div>

	<!-- Wave Pattern -->
	<div class="absolute inset-0 opacity-5">
		<svg class="absolute bottom-0 w-full" viewBox="0 0 1440 320" xmlns="http://www.w3.org/2000/svg">
			<path
				fill="#ffffff"
				fill-opacity="0.3"
				d="M0,96L48,112C96,128,192,160,288,165.3C384,171,480,149,576,133.3C672,117,768,107,864,122.7C960,139,1056,181,1152,181.3C1248,181,1344,139,1392,117.3L1440,96L1440,320L1392,320C1344,320,1248,320,1152,320C1056,320,960,320,864,320C768,320,672,320,576,320C480,320,384,320,288,320C192,320,96,320,48,320L0,320Z"
			></path>
		</svg>
	</div>

	<div class="container relative z-10 mx-auto px-4 text-center">
		<Badge
			variant="outline"
			class="hero-badge mb-8 border-white/40 bg-white/10 px-6 py-2 text-xs font-bold tracking-widest text-white/90 backdrop-blur-sm"
		>
			TERHUBUNG DENGAN KAMI
		</Badge>
		<h1 class="hero-title mb-8 text-6xl font-black tracking-tight text-white md:text-7xl">
			Hubungi Kami
		</h1>
		<div
			class="shadow-red mx-auto mb-8 h-1 w-40 bg-gradient-to-r from-transparent via-red-500 to-transparent"
		></div>
		<p class="hero-description mx-auto max-w-2xl text-xl text-gray-300 md:text-2xl">
			Ada pertanyaan atau ingin bergabung? Kami siap mendengarkan Anda
		</p>
	</div>
</section>

<!-- Contact Info Cards -->
<section class="bg-white py-24">
	<div class="container mx-auto px-4">
		<div class="mx-auto grid max-w-6xl grid-cols-1 gap-8 md:grid-cols-2 lg:grid-cols-4">
			{#each contacts as contact, i}
				<a
					href={contact.link}
					class="contact-card group {contact.link === '#' ? 'pointer-events-none' : ''}"
					style="animation-delay: {i * 0.1}s;"
				>
					<Card
						class="relative h-full overflow-hidden rounded-3xl border-2 border-gray-100 bg-white text-center transition-all duration-500 hover:-translate-y-3 hover:border-red-500 hover:shadow-2xl"
					>
						<!-- Gradient Background on Hover -->
						<div
							class="absolute inset-0 bg-gradient-to-br {contact.gradient} opacity-0 transition-opacity duration-500 group-hover:opacity-5"
						></div>

						<!-- Glow Effect -->
						<div
							class="absolute -right-16 -top-16 h-40 w-40 rounded-full bg-red-500/20 opacity-0 blur-3xl transition-opacity duration-500 group-hover:opacity-100"
						></div>

						<CardContent class="relative p-10">
							<div class="mb-6 text-6xl transition-all duration-500 group-hover:scale-125">
								{contact.icon}
							</div>
							<h3 class="mb-4 text-xl font-black text-gray-900">{contact.title}</h3>
							<div
								class="mx-auto mb-4 h-1 w-16 rounded-full bg-gray-300 transition-all duration-500 group-hover:w-full group-hover:bg-red-500"
							></div>
							<p class="text-sm leading-relaxed text-gray-600">{contact.value}</p>
						</CardContent>
					</Card>
				</a>
			{/each}
		</div>
	</div>
</section>

<!-- Contact Form & Info -->
<section class="bg-gradient-to-b from-white to-gray-50 py-32">
	<div class="container mx-auto px-4">
		<div class="mx-auto grid max-w-7xl grid-cols-1 gap-16 lg:grid-cols-2">
			<!-- Contact Form -->
			<div class="form-section">
				<div class="mb-12">
					<Badge
						class="bg-gradient-to-r from-gray-800 to-black px-4 py-2 text-xs font-bold tracking-widest text-white shadow-lg"
					>
						FORMULIR KONTAK
					</Badge>
				</div>
				<h2 class="mb-8 text-5xl font-black text-gray-900">Kirim Pesan</h2>
				<div
					class="shadow-red mb-12 h-1 w-24 rounded-full bg-gradient-to-r from-red-500 to-red-600"
				></div>

				{#if submitted}
					<Card
						class="rounded-3xl border-2 border-green-500 bg-gradient-to-br from-green-50 to-white shadow-2xl"
					>
						<CardContent class="p-12 text-center">
							<div class="mb-6 flex justify-center">
								<div class="flex h-20 w-20 items-center justify-center rounded-full bg-green-500">
									<CheckCircle2 class="h-12 w-12 text-white" />
								</div>
							</div>
							<h3 class="mb-4 text-3xl font-black text-gray-900">Pesan Terkirim!</h3>
							<p class="text-lg leading-relaxed text-gray-700">
								Terima kasih telah menghubungi kami. Kami akan segera merespons pesan Anda.
							</p>
						</CardContent>
					</Card>
				{:else}
					<form on:submit={handleSubmit} class="space-y-6">
						<div>
							<Label for="name" class="mb-2 text-sm font-bold text-gray-900">Nama Lengkap *</Label>
							<Input
								type="text"
								id="name"
								bind:value={formData.name}
								required
								class="h-14 rounded-2xl border-2 border-gray-200 bg-white px-6 transition-all duration-300 focus:border-red-500 focus:ring-2 focus:ring-red-500/20"
								placeholder="Masukkan nama lengkap Anda"
							/>
						</div>

						<div>
							<Label for="email" class="mb-2 text-sm font-bold text-gray-900">Email *</Label>
							<Input
								type="email"
								id="email"
								bind:value={formData.email}
								required
								class="h-14 rounded-2xl border-2 border-gray-200 bg-white px-6 transition-all duration-300 focus:border-red-500 focus:ring-2 focus:ring-red-500/20"
								placeholder="nama@email.com"
							/>
						</div>

						<div>
							<Label for="phone" class="mb-2 text-sm font-bold text-gray-900">Nomor Telepon</Label>
							<Input
								type="tel"
								id="phone"
								bind:value={formData.phone}
								class="h-14 rounded-2xl border-2 border-gray-200 bg-white px-6 transition-all duration-300 focus:border-red-500 focus:ring-2 focus:ring-red-500/20"
								placeholder="08xx-xxxx-xxxx"
							/>
						</div>

						<div>
							<Label for="subject" class="mb-2 text-sm font-bold text-gray-900">Perihal *</Label>
							<Select type="single" bind:value={formData.subject}>
								<SelectTrigger
									class="h-14 rounded-2xl border-2 border-gray-200 bg-white px-6 transition-all duration-300 focus:border-red-500 focus:ring-2 focus:ring-red-500/20"
								>
									{formData.subject || 'Pilih perihal'}
								</SelectTrigger>
								<SelectContent>
									{#each subjects as subject}
										<SelectItem value={subject}>{subject}</SelectItem>
									{/each}
								</SelectContent>
							</Select>
						</div>

						<div>
							<Label for="message" class="mb-2 text-sm font-bold text-gray-900">Pesan *</Label>
							<Textarea
								id="message"
								bind:value={formData.message}
								required
								rows={6}
								class="resize-none rounded-2xl border-2 border-gray-200 bg-white px-6 py-4 transition-all duration-300 focus:border-red-500 focus:ring-2 focus:ring-red-500/20"
								placeholder="Tuliskan pesan Anda di sini..."
							/>
						</div>

						<Button
							type="submit"
							size="lg"
							class="h-14 w-full rounded-full bg-gradient-to-r from-red-500 to-red-600 text-lg font-bold text-white shadow-xl transition-all duration-300 hover:scale-105 hover:shadow-2xl hover:shadow-red-500/50"
						>
							Kirim Pesan
						</Button>
					</form>
				{/if}
			</div>

			<!-- Info & Map -->
			<div class="info-section space-y-8">
				<!-- Map Placeholder -->
				<Card class="overflow-hidden rounded-3xl border-2 border-gray-200 shadow-xl">
					<div class="flex h-80 items-center justify-center bg-gray-100">
						<iframe
							src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3960.503650537753!2d107.55059921195394!3d-6.949760568011692!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x2e68ef6a211565e9%3A0xcae4b2d423ed6d24!2sPerpustakaan%20komunitas%20satu%20misi!5e0!3m2!1sid!2sid!4v1759290921472!5m2!1sid!2sid"
							width="100%"
							height="100%"
							style="border:0;"
							allow="fullscreen"
							loading="lazy"
							referrerpolicy="no-referrer-when-downgrade"
							class="rounded-3xl"
							title="Peta lokasi Perpustakaan Komunitas Satu Misi"
						></iframe>
					</div>
				</Card>

				<!-- Office Hours -->
				<Card class="rounded-3xl border-2 border-gray-200 shadow-xl">
					<CardHeader class="border-b-2 border-gray-100 p-8">
						<CardTitle class="text-2xl font-black text-gray-900">Jam Operasional</CardTitle>
						<div class="mt-3 h-1 w-20 rounded-full bg-red-500"></div>
					</CardHeader>
					<CardContent class="p-8">
						<div class="space-y-4">
							{#each officeHours as hour}
								<div
									class="flex items-center justify-between rounded-2xl bg-gray-50 p-4 transition-colors hover:bg-gray-100"
								>
									<span class="font-semibold text-gray-700">{hour.day}</span>
									<span class="font-black {hour.open ? 'text-gray-900' : 'text-gray-400'}">
										{hour.time}
									</span>
								</div>
							{/each}
						</div>
					</CardContent>
				</Card>

				<!-- Social Media -->
				<Card class="rounded-3xl border-2 border-gray-200 shadow-xl">
					<CardHeader class="border-b-2 border-gray-100 p-8">
						<CardTitle class="text-2xl font-black text-gray-900">Media Sosial</CardTitle>
						<div class="mt-3 h-1 w-20 rounded-full bg-red-500"></div>
					</CardHeader>
					<CardContent class="p-8">
						<div class="space-y-4">
							{#each socialMedia as social}
								<a
									href={social.link}
									target="_blank"
									rel="noopener noreferrer"
									class="group flex items-center gap-5 rounded-2xl bg-gray-50 p-4 transition-all duration-300 hover:-translate-x-2 hover:bg-red-50 hover:shadow-lg"
								>
									<div
										class="flex h-14 w-14 items-center justify-center rounded-full bg-white text-3xl shadow-md transition-all duration-300 group-hover:scale-110 group-hover:bg-red-500"
									>
										<svelte:component
											this={social.icon}
											class="h-6 w-6 text-gray-700 group-hover:text-white"
										/>
									</div>
									<div class="flex-1">
										<div
											class="font-black text-gray-900 transition-colors group-hover:text-red-600"
										>
											{social.name}
										</div>
										<div class="text-sm text-gray-600">{social.handle}</div>
									</div>
									<span
										class="text-2xl opacity-0 transition-all duration-300 group-hover:translate-x-2 group-hover:opacity-100"
										>→</span
									>
								</a>
							{/each}
						</div>
					</CardContent>
				</Card>
			</div>
		</div>
	</div>
</section>

<!-- CTA Section -->
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
		<h2 class="mb-8 text-5xl font-black text-white md:text-6xl">Ingin Bergabung dengan Kami?</h2>
		<div
			class="shadow-red mx-auto mb-10 h-1 w-40 rounded-full bg-gradient-to-r from-transparent via-red-500 to-transparent"
		></div>
		<p class="mx-auto mb-14 max-w-3xl text-2xl font-light leading-relaxed text-gray-300">
			Menjadi relawan atau mitra adalah cara terbaik untuk berkontribusi langsung dalam misi
			literasi kami
		</p>
		<div class="flex flex-col justify-center gap-6 sm:flex-row">
			<Button
				size="lg"
				class="group relative overflow-hidden rounded-full border-2 border-white bg-white px-12 py-7 text-lg font-bold text-black shadow-2xl transition-all duration-500 hover:scale-110"
			>
				<span class="relative z-10 flex items-center gap-2">
					Lihat Program
					<span class="transition-transform duration-300 group-hover:translate-x-2">→</span>
				</span>
			</Button>
			<Button
				size="lg"
				class="rounded-full border-2 border-red-500 bg-red-500 px-12 py-7 text-lg font-bold text-white shadow-2xl transition-all duration-500 hover:scale-110 hover:border-red-600 hover:bg-red-600"
			>
				Tentang Kami
			</Button>
		</div>
	</div>
</section>

<style>
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

	@keyframes card-appear {
		from {
			opacity: 0;
			transform: translateY(40px);
		}
		to {
			opacity: 1;
			transform: translateY(0);
		}
	}

	.hero-badge {
		animation: fade-in-up 0.8s ease-out 0.1s forwards;
		opacity: 0;
	}

	.hero-title {
		animation: fade-in-up 1s ease-out 0.3s forwards;
		opacity: 0;
	}

	.hero-description {
		animation: fade-in-up 1s ease-out 0.5s forwards;
		opacity: 0;
	}

	.contact-card {
		animation: card-appear 0.8s ease-out forwards;
		opacity: 0;
	}

	.form-section {
		animation: fade-in-up 1s ease-out 0.2s forwards;
		opacity: 0;
	}

	.info-section {
		animation: fade-in-up 1s ease-out 0.4s forwards;
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

	.shadow-red {
		box-shadow:
			0 0 20px rgba(239, 68, 68, 0.5),
			0 0 40px rgba(239, 68, 68, 0.3);
	}
</style>
