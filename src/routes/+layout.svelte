<script lang="ts">
	import './layout.css';
	import favicon from '$lib/assets/favicon.svg';
        import Header from "./Header.svelte";

	let { children } = $props();
        let user = $state({ fullName: "Juan Doe", stats: { points: 42, hours: 7 }, avatarImgUrl: "https://flowbite-svelte.com/images/profile-picture-3.webp" });
</script>

<svelte:head><link rel="icon" href={favicon} /></svelte:head>

<Header {user} />
{@render children()}
