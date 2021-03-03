<script>
	//import Tailwindcss from './helpers/Tailwindcss.svelte';
	import Router from 'svelte-spa-router'
	import Nav from './helpers/Nav.svelte'
	import Index from './pages/Index.svelte'

	const routes = {
    '/': Index,
	}

</script>

<!-- <Tailwindcss /> -->
<Nav/>
<Router {routes}/>
