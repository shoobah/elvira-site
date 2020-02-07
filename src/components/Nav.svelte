<script>
  export let segment;
</script>

<style>
  .top {
    background-color: #a5a5a5;
    color: rgb(0, 0, 0);
    grid-column: left / right;
    grid-row: top;
    display: flex;
  }

  .heading {
    font-family: dienstag, sans-serif;
    font-weight: 100;
    font-style: normal;
    font-size: 70px;
    color: #fafafa;
    position: relative;
    top: 5px;
    margin: 0;
    padding-left: 10px;
  }
  .app-logo {
    border-radius: 50%;
    width: 80px;
    height: 80px;
    position: relative;
    top: 10px;
    padding-left: 10px;
  }

  .menu {
    height: 30px;
    background-color: #585858;
    color: #fff;
    grid-column: left / right;
    grid-row: menu;
    display: grid;
    grid-template-columns: repeat(10, 150px);
    font-weight: bold;
    text-transform: uppercase;
    padding-left: 5px;
  }

  span {
    position: relative;
    top: 2px;
    padding-top: 2px;
    text-align: center;
  }

  a {
    color: #fff;
    cursor: pointer;
    text-decoration: none;
  }

  a:hover,
  .selected {
    text-decoration: underline;
  }
</style>

<div class="top">
  <img src="/image/_DSC1579.32ba4a92.png" class="app-logo" alt="logo" />
  <div class="heading">ELVIRA ROOS</div>
</div>
<div class="menu">
  <span>
    <a rel="prefetch" class={segment === undefined ? 'selected' : ''} href="/">
      image-gallery
    </a>
  </span>
  <span>
    <a rel="prefetch" class={segment === 'cv' ? 'selected' : ''} href="cv">
      cv / reel
    </a>
  </span>
</div>
