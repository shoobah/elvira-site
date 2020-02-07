<script>
  import { createEventDispatcher } from "svelte";
  import Thumbnail from "./thumbnail.svelte";

  const dispatch = createEventDispatcher();

  export let images = {};

  function imageClicked(e) {
    dispatch("select", {
      url: e.detail.baseUrl + ".jpg"
    });
  }
</script>

<style>
  .image-grid {
    display: grid;
    grid-gap: 5px;
    grid-template-rows: 92px;
    grid-template-columns: auto;
    align-content: start;
  }
</style>

<div class="image-grid">
  {#if images.filenames}
    {#each images.filenames as i}
      <Thumbnail baseUrl={i} on:click={imageClicked} />
    {/each}
  {/if}
</div>
