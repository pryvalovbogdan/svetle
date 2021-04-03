<script>
	import '../app.css';
	import NavBar from '$lib/NavBar.svelte';
</script>

<main>
	<NavBar />
	<slot />
</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		margin: 0 auto;
	}
</style>
