<script>
	import Link from './Link.svelte';
	import Route from './Route.svelte';
	export let name;
</script>

<style>
</style>

<!-- Navigation goes here -->
<Link page={{path: '/', name: 'Home'}} />
<Link page={{path: '/about', name: 'About'}} />

<!-- Main container goes here -->
<Route />