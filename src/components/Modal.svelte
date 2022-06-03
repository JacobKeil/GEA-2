<script>
	import { createEventDispatcher } from 'svelte';
	import { fly } from 'svelte/transition';
	const dispatch = createEventDispatcher();

	function closeModal(e) {
		if (e.target.classList.contains('modal')) {
			dispatch('closeModal');
		}
	}
</script>

<div
	in:fly={{ x: -200, duration: 200 }}
	out:fly={{ x: 200, duration: 200 }}
	class="modal"
	on:click={closeModal}
>
	<slot />
</div>

<style>
	.modal {
		position: fixed;
		padding: 2rem;
		top: 0;
		bottom: 0;
		left: 0;
		right: 0;
		background: #000000d8;
		display: flex;
		justify-content: center;
		align-items: center;
		z-index: 100;
	}
</style>