<script>
  import Navbar from '../components/Navbar.svelte';
  import Modal from '../components/Modal.svelte';
  import MobileMenu from '../components/MobileMenu.svelte';
  let isShowingMobile = false;
</script>

<section class="main-screen">
  <Navbar on:openModal={() => isShowingMobile = true} />
  <div class="center-wrapper">
		<div class="main-wrapper">
			<slot />
		</div>
	</div>
</section>

{#if isShowingMobile}
	<Modal on:closeModal={() => isShowingMobile = false}>
		<MobileMenu on:closeModal={() => isShowingMobile = false}/>
	</Modal>
{/if}

<style global>
	@import url('https://fonts.googleapis.com/css2?family=Kdam+Thmor+Pro&display=swap');

	* {
		font-family: 'Kdam Thmor Pro', sans-serif;
		margin: 0;
		padding: 0;
	}

  :root {
		--main-dark-blue: #222831;
		--main-light-blue: #414a57;
		--main-grey: #393e46;
		--main-orange: #ee7b17;
		--sec-orange: #fa6bff;
		--main-off-white: #dbdbdb;
		--main-light-grey: #bebebe;
		--main-light-red: #ca4444;
	}

  .main-screen {
    background-color: rgb(240, 239, 255);
		min-height: 100vh;
	}

	.main-wrapper {
		max-width: 1200px;
		padding: 1rem;
	}

	.center-wrapper {
		display: flex;
		flex-direction: column;
		align-items: center;
		width: 100%;
	}
</style>