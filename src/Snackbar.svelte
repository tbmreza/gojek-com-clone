<style>
  .snackbar {
    position: fixed;
    bottom: 0;
    right: 1em;
    left: 1em;
    padding: 1em;
    border-top-left-radius: 18px;
    border-top-right-radius: 18px;
    background: white;
    box-shadow: var(--box-shadow);
    border: 1px solid #cdc;
  }
</style>

<div class="snackbar" role="dialog" aria-modal="true">
  <div>
    <slot />
  </div>
</div>
