<script>
  export let w = 0;
  import Times from "./TimesIcon.svelte";

  let hide = false;
  function x() {
    hide = true;
  }
</script>

<style>
  .snackbar {
    background-color: #fff;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
    border: 1px solid #cdc;
    box-shadow: 1px 4px 10px 1px rgba(0, 0, 0, 0.2);
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .left {
    display: flex;
    align-items: center;
  }
  .left > *,
  .snackbar__btn > * {
    margin: 2px 8px;
  }
  .snackbar__x,
  .snackbar button {
    cursor: pointer;
  }
  .snackbar__logo > img {
    width: 64px;
    margin: 8px 0;
  }
  .snackbar__caption > p {
    font-size: 10px;
    margin: 0;
  }
  .snackbar__caption > * {
    margin: 0;
  }
  @media (min-width: 650px) {
    .snackbar {
      display: none;
    }
  }
  .hide {
    display: none;
  }
</style>

<div class="snackbar" style="width:{w}px;" class:hide>
  <div class="left">
    <div class="snackbar__x" on:click={x}>
      <Times />
    </div>
    <div class="snackbar__logo">
      <img alt="Gojek App" src="static/images/Gojek_ID2x.jpg" />
    </div>
    <div class="snackbar__caption">
      <h5>Gojek App</h5>
      <p>One app for every need</p>
    </div>
    <div />
  </div>

  <div class="snackbar__btn">
    <a href="https://www.gojek.com/">
      <button>Open</button>
    </a>
  </div>
</div>
