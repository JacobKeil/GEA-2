<script>
  import { goto } from '$app/navigation';
  import { createEventDispatcher } from 'svelte';
	const dispatch = createEventDispatcher();

  function nav(path) {
    goto(path);
    dispatch("closeModal")
  }
</script>

<ul>
  <li on:click={() => nav("/")}>Home</li>
  <li on:click={() => nav("/research")}>Research</li>
  <li on:click={() => nav("/examples")}>Examples</li>
  <li on:click={() => nav("/facts")}>Facts</li>
  <li on:click={() => nav("/response")}>Response</li>
  <li on:click={() => nav("/references")}>References</li>
</ul>

<style>
  ul {
    display: flex;
    flex-direction: column;
    align-items: center;
    padding: 1rem;
    border-radius: .5rem;
  }

  li {
    cursor: pointer;
    font-size: 2rem;
    color: rgb(216, 216, 216);
    list-style: none;
    transition: color .3s ease;
  }

  li:hover {
    color: var(--sec-orange);
  }
</style>