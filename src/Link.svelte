<script>
  import { curRoute } from './store';
  export let page;

  function redirectTo(event){
    // change current router path
    curRoute.set(event.target.pathname);
    // push the path into web browser history API
    window.history.pushState({path: page.path}, '', window.location.origin + page.path);
  }
</script>

<style>
a {
  text-transform: uppercase;
  text-decoration: underline;
  padding: 1rem;
}
</style>

<a href={page.path} on:click|preventDefault={redirectTo}>{page.name}</a>