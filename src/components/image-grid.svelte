<script>
  import { createEventDispatcher } from "svelte";
  import Thumb from "./thumbnail.svelte";

  const dispatch = createEventDispatcher();

  export let cssClass = "";
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
    grid-template-columns: 92px;
    align-content: start;
  }
</style>

<div class="{cssClass} image-grid">
  {#if images.filenames}
    {#each images.filenames as i}
      <Thumb baseUrl={i} on:click={imageClicked} />
    {/each}
  {/if}
</div>
