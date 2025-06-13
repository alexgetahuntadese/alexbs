<script>
	import Counter from '$lib/Counter.svelte';
 import { bettingSites } from '$lib/allBettingSites.js';
  import BettingSite from '$lib/BettingSite.svelte';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<section>
<h1><span class="welcome"><picture>
<source srcset="svelte-welcome.webp" type="image/webp" />
<img src="svelte-welcome.png" alt="Welcome" /> </picture>
</span></h1>
</section>
<section>
<h1> All betting sites in Ethiopia! Play Here </h2>
</section>
<section class="link-container">
  {#each bettingSites as site}
    <BettingSite name={site.name} url={site.url} bonus={site.bonus} />
  {/each}
</section>

<style>
	section {
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: center;
		flex: 1;
	}
.link-container {
    display: flex;
    flex-wrap: wrap; /* Allows items to wrap to the next row */
    justify-content: center; /* Center items on each row */
    gap: 1rem; /* Spacing between items */
  }

  .link-item {
    display: flex;
    flex-direction: row; /* Place link and bonus info side by side */
    align-items: center;
    gap: 0.5rem; /* Space between link and bonus info */
    flex: 1 1 calc(50% - 1rem); /* Each item takes 50% of the row minus the gap */
  }

  .link-item a {
    text-decoration: none;
    color: var(--accent-color);
    font-size: 1.2rem;
  }

  .link-item p {
    margin: 0;
    font-size: 1rem;
    color: var(--text-color);
  }

	h1 {
		width: 100%;
	}
	.welcome {
		display: block;
		position: relative;
		width: 100%;
		height: 0;
		padding: 0 0 calc(100% * 495 / 2048) 0;
	}

	.welcome img {
		position: absolute;
		width: 100%;
		height: 100%;
		top: 0;
		display: block;
	}

</style>
