<script context="module">
	export async function load({ session }) {
		if (!session.authenticated) {
			return {
				props: {
				authenticated: false
			}
			};
		}
		return {
			props: {
				authenticated: session.authenticated,
				name: session.user.name
			}
		};
	}
</script>

<script>
	import Nav from '../components/nav.svelte';
	import '../assets/css/global.scss';
	export let authenticated;
	export let name;
</script>

{#if authenticated}
	<Nav {name} />
{/if}
<slot />
