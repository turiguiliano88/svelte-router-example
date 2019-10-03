<script>
  import { onDestroy } from 'svelte';
  import { curRoute } from './store';
  import router from './router';

  let component;
  const unsubscribe = curRoute.subscribe(value => {
    component = router.filter(r => r.path === $curRoute)[0].component;
  })

  onDestroy(unsubscribe);
</script>

<style>
</style>

<div class="main-container">
  <svelte:component this={component} />
</div>