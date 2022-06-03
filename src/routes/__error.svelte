<script context="module">
	export function load({ error, status }) {
		return {
			props: {
				message: error.message,
				status
			}
		};
	}
</script>

<script>
	import NotFound from '../components/NotFound.svelte';
	import Error from '../components/Error.svelte';

	export let message;
	export let status;
</script>

{#if status == 404}
	<NotFound />
{:else}
	<Error {message} {status} />
{/if}