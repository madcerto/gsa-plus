<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
        import Header from "./Header.svelte";
        import sampleUser from "./sampleUser.json";

	let { children } = $props();
        let user = $state(sampleUser);
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<Header {user} />
<main class="max-w-[1280px] mx-auto">
    {@render children()}
</main>
