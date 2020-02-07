<script>
  import images from "../components/images.json";
  import ImageGrid from "../components/image-grid.svelte";
  import BigImage from "../components/big-image.svelte";

  let selectedImage = images.filenames[0] + ".jpg";

  function imageSelected(e) {
    selectedImage = e.detail.url;
  }
</script>

<style>
  .image-gallery {
    display: grid;
    grid-template-rows: [grid] 100px [image] 6fr;
    grid-template-columns: auto;
  }

  .the-grid-wrapper {
    grid-row: grid;
    padding: 0 5px;
  }
  .the-image-wrapper {
    grid-row: image;
  }
</style>

<div class="image-gallery">
  <div class="the-grid-wrapper">
    <ImageGrid {images} on:select={imageSelected} />
  </div>
  <div class="the-image-wrapper">
    <BigImage url={selectedImage} />
  </div>
</div>
