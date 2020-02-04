<script>
  import { beforeUpdate, afterUpdate, tick } from "svelte";
  import { fade } from "svelte/transition";
  export let url = "";

  let visible = true;

  beforeUpdate(() => {
    // visible = false;
    console.log("before visible", visible);
  });

  afterUpdate(() => {
    // visible = true;
    console.log("after visible", visible);
  });
</script>

<style>
  .the-image-wrapper {
    margin-left: 5px;
    grid-column-start: image;
  }

  .the-image {
    width: 98%;
    border: solid 1px black;
    animation-name: fadeIn;
    animation-iteration-count: 1;
    animation-timing-function: ease-in-out;
    animation-duration: 1s;
    animation-fill-mode: forwards;
  }

  @keyframes fadeIn {
    0% {
      opacity: 0;
    }
    100% {
      opacity: 1;
    }
  }
</style>

<div class="the-image-wrapper">
  {#if visible}
    <img src={url} class="the-image" alt="" />
  {/if}
</div>
