<script>
	import { page } from '$app/stores';
  import { fade } from 'svelte/transition';
  import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();
  import banner from '../images/Gaming-addiction.jpg';

  let x;
  let y;
</script>

<svelte:window bind:scrollY={y} bind:innerWidth={x}/>

{#if y < 350}
  {#if x < 650}
    <div class="mobile-menu" transition:fade on:click={() => dispatch("openModal")}>
      <i class='bx bx-menu'></i>
    </div>
  {:else}
    <nav transition:fade>
      <ul>
        <li class:active={$page.url.pathname === '/'}><a sveltekit:prefetch href="/">Home</a></li>
        <li class:active={$page.url.pathname === '/research'}>
          <a sveltekit:prefetch href="/research">Research</a>
        </li>
        <li class:active={$page.url.pathname === '/examples'}>
          <a sveltekit:prefetch href="/examples">Examples</a>
        </li>
        <li class:active={$page.url.pathname === '/facts'}>
          <a sveltekit:prefetch href="/facts">Facts</a>
        </li>
        <li class:active={$page.url.pathname === '/response'}>
          <a sveltekit:prefetch href="/response">Response</a>
        </li>
        <li class:active={$page.url.pathname === '/references'}>
          <a sveltekit:prefetch href="/references">References</a>
        </li>
      </ul>
    </nav>
  {/if}
{/if}

<header style="background-image: url({banner});">
  <div class="center-fixed">
    <h2 class="title">Gaming Disorders</h2>
    <div class="social">
      <i class='bx bxl-twitter' on:click={() => {
        window.open("https://twitter.com/jacobkusf", '_blank')
      }}></i>
      <i class='bx bxl-youtube' on:click={() => {
        window.open("https://www.youtube.com/channel/UC3bRc4fIVY403PzyujLcuaA", '_blank')
      }}></i>
    </div>
  </div>
</header>

<style>
	header {
    background-position: center;
    background-repeat: no-repeat;
    background-size: cover;
    height: 25rem;
		display: flex;
		justify-content: center;
    align-items: center;
	}

	nav {
		display: flex;
		--background: rgb(230, 230, 230);
	}

	ul {
    left: 50%;
    transform: translateX(-50%);
    border-radius: 0 0 10px 10px;
		position: fixed;
    top: 0;
		height: 3em;
		display: flex;
		list-style: none;
		background: var(--background);
    z-index: 99;
	}

	li {
    color: #1d1d1d;
		position: relative;
		height: 100%;
	}

	li.active::before {
		--size: 6px;
		content: '';
		width: 0;
		height: 0;
		position: absolute;
		top: 0;
		left: calc(50% - var(--size));
		border: var(--size) solid transparent;
		border-top: var(--size) solid var(--sec-orange);
	}

	nav a {
		display: flex;
		height: 100%;
		align-items: center;
		padding: 0 1em;
		color: var(--heading-color);
		font-weight: 700;
		font-size: 0.8rem;
		text-transform: uppercase;
		letter-spacing: 0.1em;
		text-decoration: none;
		transition: color 0.2s linear;
	}

	a:hover {
		color: var(--sec-orange);
	}

  .mobile-menu {
    color: #ececec;
    border-radius: 0 0 10px 10px;
		position: fixed;
    top: 10px;
    right: 10px;
		height: 3em;
		display: flex;
		list-style: none;
		background: var(--background);
    z-index: 99;
  }

  .center-fixed {
    width: 100%;
    height: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    color: #ececec;
    background-color: #1d1d1dab;
  }

  .social {
    color: #ececec;
    display: flex;
    justify-content: space-between;
  }

  .social i {
    transition: all .3s ease;
  }

  i:hover {
    cursor: pointer;
    color: var(--sec-orange);
  }

  .bx {
    font-size: 2rem;
  }

  .title {
    font-size: 2rem;
  }
</style>