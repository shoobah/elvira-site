<script>
  import Nav from "../components/Nav.svelte";

  export let segment;
</script>

<style>
  .all {
    display: grid;
    grid-template-rows: [top] 100px [menu] 30px [main] auto;
    grid-template-columns: [left] auto [center] 95% [right] auto;
    grid-row-gap: 0px;
    position: relative;
  }

  main {
    padding-top: 5px;
    grid-row: main;
    grid-column: left / right;
  }
</style>

<div class="all">
  <Nav {segment} />
  <main>
    <div>
      <slot />
    </div>
  </main>
</div>
