<script lang="ts">
	import '../app.css';
	import Lettermark from '$lib/components/Lettermark.svelte';
	import { Bell, Book, Bookmark, Headphones, Image, Search, Share, Video } from '@lucide/svelte';
	import type { Component } from 'svelte';

	interface ItemI {
		icon: Component;
		text: string;
	}

	const actions: ItemI[] = [
		{
			icon: Search,
			text: 'Search'
		},
		{
			icon: Bookmark,
			text: 'Save'
		},
		{
			icon: Share,
			text: 'Share'
		},
		{
			icon: Bell,
			text: 'Notifications'
		}
	];

	interface LinkI extends ItemI {
		href: string;
	}

	const links: LinkI[] = [
		{
			href: '/texts',
			icon: Book,
			text: 'Texts'
		},
		{
			href: '/audio',
			icon: Headphones,
			text: 'Audio'
		},
		{
			href: '/videos',
			icon: Video,
			text: 'Videos'
		},
		{
			href: '/images',
			icon: Image,
			text: 'Images'
		}
	];

	let { children } = $props();
</script>

<header
	class="shadow-purple-med/50 fixed bottom-1 left-1 top-1 flex w-7 flex-col items-center gap-2 rounded-lg bg-white shadow"
>
	<a
		href="/"
		class="bg-purple-min flex size-7 items-center justify-center rounded-b-none rounded-t-lg text-white"
	>
		<span class="sr-only">Home</span>
		<Lettermark class="size-4" colors={{ bottom: '--color-purple-min', top: '--color-white' }} />
	</a>
	<ol class="grid gap-1">
		{#each actions as action}
			<li>
				<button
					class="hover:bg-purple-max text-purple-min group relative flex size-5 items-center justify-center rounded transition-colors"
				>
					<span
						class="not-group-hover:opacity-0 rounded-xs absolute left-6 block bg-white p-1 text-sm opacity-100 shadow-lg transition-all"
						>{action.text}</span
					>
					<action.icon class="size-2" />
				</button>
			</li>
		{/each}
	</ol>
	<nav class="border-purple-max border-t pt-2">
		<ol class="grid gap-1">
			{#each links as link}
				<li>
					<a
						class="hover:bg-purple-max text-purple-min group relative flex size-5 items-center justify-center rounded transition-colors"
						href={link.href}
					>
						<span
							class="not-group-hover:opacity-0 rounded-xs absolute left-6 block bg-white p-1 text-sm opacity-100 shadow-lg transition-all"
							>{link.text}</span
						>
						<link.icon class="size-2" />
					</a>
				</li>
			{/each}
		</ol>
	</nav>
</header>
<main class="py-3 pl-12 pr-4">
	{@render children()}
</main>
