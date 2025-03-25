<script lang="ts">
	import type { ClassValue } from 'svelte/elements';

	let props: { class: ClassValue } = $props();
</script>

<svg
	class={props.class}
	width="100%"
	height="100%"
	viewBox="0 0 32 32"
	xmlns="http://www.w3.org/2000/svg"
>
	<defs>
		<linearGradient id="gradient" gradientTransform="rotate(90)">
			<stop offset="0%" stop-color="var(--color-white)" />
			<stop offset="100%" stop-color="var(--color-purple-min)" />
		</linearGradient>
	</defs>
	<g
		id="line"
		style="stroke-linecap:round;stroke-linejoin:round;stroke-miterlimit:1.5;"
		transform="matrix(-1,0,0,1,40,-8)"
	>
		<path
			d="M28.81,28.409C33.202,30.027 38.188,31.807 39.5,39.5C37,25 32,20 29,18C26,16 26.016,13.099 23,11C20.096,8.979 17.343,11.54 8.5,8.5C18.402,11.873 21.7,13.453 21.5,20.5C21.5,20.817 21.513,21.119 21.538,21.408"
			stroke="url(#gradient)"
			class="stroke-width-1 fill-none"
		/>
		<path
			d="M32.5,27.5C24,27.5 24,39.5 8.5,39.5C16,39.5 16,20.5 24.5,20.5"
			stroke="url(#gradient)"
			class="stroke-width-1 fill-none"
		/>
	</g>
</svg>
