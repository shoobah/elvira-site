<script>
  export let baseUrl = "";
  let imageUrl = baseUrl + "s.jpg";
  let isBig = false;

  function viewBig() {
    if (imageUrl.indexOf("s.") > 0) {
      imageUrl = baseUrl + ".jpg";
      isBig = true;
    } else {
      imageUrl = baseUrl + "s.jpg";
      isBig = false;
    }
  }

  // document.addEventListener("contextmenu", event => event.preventDefault());
</script>

<style>
  img {
    transition: all 0.1s;
    border-radius: 5px;
    border: solid 1px black;
    cursor: pointer;
  }

  .smallImage:hover {
    transform: scale(1.1);
  }

  .bigImage {
    width: 100%;
  }
</style>

<img
  on:contextmenu={e => {
    e.preventDefault();
  }}
  src={imageUrl}
  class:bigImage={isBig}
  class:smallImage={!isBig}
  on:click={viewBig}
  alt="elvira" />
