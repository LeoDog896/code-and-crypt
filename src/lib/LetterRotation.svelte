<script lang="ts">
  export let alphabet: string[] = "ABCDEFGHIJKLMNOPQRSTUVWXYZ".split("")
  export let index = 0;

  // size (in px)
  export let size = 500;
</script>

<div>
  <div style="width: {size}px">
    {#each alphabet as letter, i}
      {#if i == index}
        <span class="parent"><span class="active">{letter}</span></span>
      {:else}
        <span class="parent"><span>{letter}</span></span>
      {/if}
    {/each}
  </div>

  <div class="notch"></div>
</div>
<style>

  .notch {
    position: absolute;
    left: 250px;
    transform: translate-x(-50%);
    background-color: blue;
    width: 50px;
    height: 50px;
  }

  div {
    font-family: monospace;
    overflow-x: scroll;
    height: 500px;
    white-space: nowrap;
    position: relative;
  }

  span.parent {
    padding: 0rem 1rem;
    position: relative;
    border-left: black solid 1px;
    border-right: black solid 1px;
    display: inline;
  }

  span.active {
    font-style: bold;
  }
</style>