<script>
  export let name;
  export let url;
  export let bonus;
</script>

<div class="site-item">
  <a href={url}>{name}</a>
  <p>{bonus}</p>
</div>

<style>
  .site-item {
    display: flex;
    flex-direction: row;
    align-items: center;
    gap: 0.5rem;
  }

  .site-item a {
    text-decoration: none;
    color: var(--accent-color);
    font-size: 1.2rem;
  }

  .site-item p {
    margin: 0;
    font-size: 1rem;
    color: var(--text-color);
  }
</style>