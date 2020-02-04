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
    grid-template-columns: [grid] 100px [image] 6fr;
  }

  .the-grid-wrapper {
    grid-column: grid;
    padding: 0 5px;
  }
  .the-image-wrapper {
    grid-column: image;
  }
</style>

<div class="image-gallery">
  <div class="the-grid-wrapper">
    <ImageGrid {images} on:select={imageSelected} cssClass="the-grid" />
  </div>
  <div class="the-image-wrapper">
    <BigImage url={selectedImage} />
  </div>
</div>
