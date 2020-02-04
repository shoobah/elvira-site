<script>
  import { createEventDispatcher } from "svelte";
  import { fade } from "svelte/transition";

  export let baseUrl = "";

  const dispatch = createEventDispatcher();

  let imageUrl = baseUrl + "s.jpg";

  function imageClick() {
    dispatch("click", {
      baseUrl: baseUrl
    });
  }
</script>

<style>
  img {
    transition: all 0.1s;
    border: solid 1px black;
    cursor: pointer;
  }

  .smallImage:hover {
    box-shadow: 0 0 10px #000000c4;
  }
</style>

<img
  transition:fade
  on:contextmenu={e => {
    e.preventDefault();
  }}
  src={imageUrl}
  class="smallImage"
  on:click={imageClick}
  alt="elvira" />
