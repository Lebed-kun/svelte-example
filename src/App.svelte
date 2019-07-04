<script>
	import { Router, Route } from 'svelte-routing';
	
	import PostList from './pages/PostList.svelte';
	import About from './pages/About.svelte';
	import Contacts from './pages/Contacts.svelte';
	import Error404 from './pages/Error404.svelte';
</script>

<Router>
	<Route exact path="/" component="{PostList}" />
	<Route exact path="/about" component="{About}"/>
	<Route exact path="/contacts" component="{Contacts}" />
	<Route component="{Error404}" />
</Router>


