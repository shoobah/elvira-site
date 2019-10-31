<script>
  import Image from "./image.svelte";

  export let images = {};
</script>

<style>
  .image-grid {
    display: grid;
    grid-gap: 5px;
    width: 50%;
    grid-template-columns: repeat(4, 92px);
  }
</style>

<div class="image-grid">
  {#if images.filenames}
    {#each images.filenames as i}
      <Image baseUrl={i} />
    {/each}
  {/if}
</div>
