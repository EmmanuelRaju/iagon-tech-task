<script>
	import { backIn, backOut } from 'svelte/easing';

	let { label, href, id, activeLink = $bindable() } = $props();

	let isActive = $derived(activeLink === id);

	function slideSpringIn(node, { duration = 300 } = {}) {
		return {
			duration,
			css: (t) => {
				const eased = backOut(t);
				return `
					transform: translateY(${(1 - eased) * 100}%);
				`;
			}
		};
	}
	function slideSpringOut(node, { duration = 300 } = {}) {
		return {
			duration,
			css: (t) => {
				const eased = backIn(t);
				const scaleEased = backOut(t * 0.25);
				return `
					transform: translateY(${(1 - eased) * 100}%) scaleX(${1 - scaleEased});
					transform-origin: center;
				`;
			}
		};
	}
</script>

<a
	{href}
	class="relative flex flex-col overflow-hidden p-10 transition-colors duration-200 hover:text-blue-500 {isActive
		? 'text-blue-500'
		: 'text-white/50'}"
	onclick={(e) => {
		e.preventDefault();
		activeLink = id;
	}}
>
	<span>{label}</span>

	{#if isActive}
		<svg
			class="absolute -bottom-0.75 left-0 h-[25%] w-full transition duration-200"
			in:slideSpringIn
			out:slideSpringOut
			viewBox="0 0 100 14"
			preserveAspectRatio="none"
			xmlns="http://www.w3.org/2000/svg"
		>
			<path d="M 0 14 C 20 14 30 1 50 1 C 70 1 80 14 100 14" fill="#fff" />
		</svg>
	{/if}
</a>
