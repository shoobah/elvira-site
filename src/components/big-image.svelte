<script>
  import { beforeUpdate, afterUpdate, tick } from "svelte";
  import { fade } from "svelte/transition";
  export let url = "";

  let visible = false;
  const loaded = new Map();

  function lazy(node, data) {
    if (loaded.has(data.src)) {
      node.setAttribute("src", data.src);
    } else {
      // simulate slow loading network
      setTimeout(() => {
        const img = new Image();
        img.src = data.src;
        img.onload = () => {
          loaded.set(data.src, img);
          node.setAttribute("src", data.src);
        };
      }, 2000);
    }

    return {
      destroy() {} // noop
    };
  }
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
    <img src={url} class="the-image" alt="" use:lazy={{ src: url }} />
  {/if}
</div>
