<script>
  import images from "../components/images.json";
  import ImageGrid from "../components/image-grid.svelte";

  let selectedImage = "";

  function imageSelected(e) {
    selectedImage = e.detail.url;
  }
</script>

<style>
  .image-gallery {
    display: grid;
    grid-template-columns: [grid] 100px [image] 6fr;
  }

  .the-grid-wrapper {
    grid-column-start: grid;
  }

  .the-image-wrapper {
    grid-column-start: image;
  }

  .the-image {
    width: 100%;
    border: solid 1px black;
  }
</style>

<div class="image-gallery">
  <div class="the-grid-wrapper">
    <ImageGrid {images} on:select={imageSelected} cssClass="the-grid" />
  </div>
  <div class="the-image-wrapper">
    {#if selectedImage}
      <img src={selectedImage} class="the-image" alt="" />
    {/if}
  </div>
</div>
