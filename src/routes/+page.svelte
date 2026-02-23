<script>
	import Link from '$lib/components/Link.svelte';
	let links = [
		{
			id: 1,
			label: 'Menu 1',
			href: '#Menu1'
		},
		{
			id: 2,
			label: 'Menu 2',
			href: '#Menu2'
		}
	];

	let activeLink = $state(1);
</script>

<svelte:head>
	<title>IAGON | Tech Task</title>
</svelte:head>

<main class="grid min-h-screen place-content-center bg-black font-display">
	<div class="overflow-hidden rounded-4xl border border-white/50 bg-black">
		<nav class="flex justify-end gap-5 px-5">
			{#each links as link (link.id)}
				<Link {...link} bind:activeLink></Link>
			{/each}
		</nav>

		<div class="h-[50vh] min-w-[60vw] rounded-t-4xl bg-white"></div>
	</div>
</main>
