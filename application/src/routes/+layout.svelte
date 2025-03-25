<script lang="ts">
	import '../app.css';
	import Lettermark from '$lib/components/Lettermark.svelte';

	let { children } = $props();
</script>

<header class="shadow-purple-med/50 fixed bottom-1 left-1 top-1 w-7 rounded-lg bg-white shadow">
	<nav>
		<ol>
			<li>
				<a
					href="/"
					class="bg-purple-min flex size-7 items-center justify-center rounded-b-none rounded-t-lg text-white"
				>
					<span class="sr-only">Home</span>
					<Lettermark class="size-4" />
				</a>
			</li>
		</ol>
	</nav>
</header>
<main class="py-3 pl-12 pr-4">
	{@render children()}
</main>
