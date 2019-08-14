<script>
	import router, { curRoute } from './router.js';
	import RouterLink from './RouterLink.svelte';
	import { onMount } from 'svelte';

	onMount(() => {
		curRoute.set(window.location.pathname);
		if (!history.state) {
			window.history.replaceState({path: window.location.pathname}, '', window.location.href)
		}
	})

	function handlerBackNavigation(event){
		curRoute.set(event.state.path)
	}
</script>

<style>
	h1 {
		color: purple;
	}
</style>

<svelte:window on:popstate={handlerBackNavigation} />

<RouterLink page={{path: '/home', name: 'Home'}} />
<RouterLink page={{path: '/about', name: 'About'}} />

<div id="pageContent">
	<svelte:component this={router[$curRoute]} />
</div>