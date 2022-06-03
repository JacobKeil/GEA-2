<script>
  import Navbar from '../components/Navbar.svelte';
  import Footer from '../components/Footer.svelte';
</script>

<section class="main-screen">
  <Navbar />
  <div class="center-wrapper">
		<div class="main-wrapper">
			<slot />
		</div>
	</div>
  <!-- <Footer /> -->
</section>

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
		--sec-orange: #dc61e0;
		--main-off-white: #dbdbdb;
		--main-light-grey: #bebebe;
		--main-light-red: #ca4444;
	}

  .main-screen {
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