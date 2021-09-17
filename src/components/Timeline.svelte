<script>
    import Card from './Card.svelte';
    export let posts = [];
</script>

<style>
  .timeLine {
    padding: 4em 0 0 0;
  }
</style>

<div class="timeline">
    <div class="timeline__container">
        {#each posts as post}
        <Card {...post}/>
        {:else}
            <p>Loading...</p>
        {/each}
    </div>
</div>
