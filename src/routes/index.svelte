
<script context="module">
    export async function load({session}){
            if(!session.authenticated){
                return{
                    status:302,
                    redirect:'/auth'
                }
            }
			return{}
    }
</script>
<script>
	import { Router, Route } from 'svelte-routing';
	import Auth from './auth.svelte';
	import Home from './home.svelte';
	import About from './about.svelte';
	import insertProducts from './insertProducts.svelte';
	import Nav from '../components/nav.svelte';
</script>
<Router>
	<main>
		<Route path="/auth" component={Auth} {Nav} />
		<Route path="/home" component={Home} {Nav} />
		<Route path="/about" component={About} />
		<Route path="/insertProducts" component={insertProducts} />
	</main>
</Router>
