<script>
	import Navbar from './Navbar.svelte';
	import Player from './Player.svelte';
	import Scoreboard from './Scoreboard.svelte';
	import { Router, Link, Route } from 'svelte-routing';
	import NewPage from './NewPage.svelte';  

	export let url = "";

</script>
<Router url="{url}">
  <nav>
    <Link to="/">Home</Link>
    <Link to="about">About</Link>
  </nav>
  <div>
    <Route path="about" component="{NewPage}" />
    <Route path="/" component="{Scoreboard}"></Route>
  </div>
</Router>


<style>
</style>