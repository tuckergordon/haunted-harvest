<script lang="ts">
  export let style = "";
</script>

<div class="scroller" {style}>
  <div class="scroller-backdrop">
    <slot name="backdrop" />
  </div>
  <div class="scroller-overlays">
    <slot name="overlays" />
  </div>
</div>

<style lang="scss">
  .scroller {
    display: block;
    position: relative;
    width: 100%;
  }

  :global {
    .scroller-backdrop {
      width: 100%;
      height: 100%;
      position: sticky;
      top: 0;
      display: block;
      width: 100%;
      height: 100vh;
      overflow: hidden;

      > * {
        width: 100%;
        height: 100%;
      }

      img {
        object-fit: cover;
      }
    }

    .scroller-overlays {
      display: block;
      width: 100%;
      min-height: 100vh;
      margin-top: -100vh;
      transform: translate3d(0, 0, 0);
      pointer-events: none;

      & > * {
        position: relative;
        width: 100%;
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
      }
    }
  }
</style>
