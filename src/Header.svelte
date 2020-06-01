<script>
  export let w = 0;
  export let ml = 0;
  export let show;
  import Hamburger from "./Hamburger.svelte";

  function click() {
    show = !show;
  }
</script>

<style>
  * {
    margin: 0;
  }
  .header {
    z-index: 1;
    position: sticky;
    top: 0;
    padding: 1em 0;
    background-color: #fff;
    display: flex;
    justify-content: space-between;
    align-items: center;
    box-shadow: var(--box-shadow);
  }
  .header__menu {
    display: flex;
    margin-left: 32px;
    width: 42ch;
    justify-content: space-between;
    align-items: center;
  }
  .header__menu > a {
    color: unset;
    font-family: MaisonNeue-Book, sans-serif;
    font-size: 14px;
  }
  .header__menu > a:hover {
    color: var(--brand-main);
    transition: 0.3s;
  }
  .header__brand img {
    margin: 6px 16px 4px 0;
  }
  .header__burger {
    display: none;
  }
  @media (max-width: 800px) {
    .header__burger {
      display: unset;
    }
  }
  .left {
    display: flex;
  }
</style>

<div class="header">
  <div class="left">
    <div class="header__brand" style="margin-left:{ml}px;">
      <img src="static/images/gojek-logo_normal.svg" alt />
    </div>
    {#if w > 800}
      <div class="header__menu">
        <a href="https://www.gojek.com/">About Us</a>
        <a href="https://www.gojek.com/">Services</a>
        <a href="https://www.gojek.com/">Blog</a>
        <a href="https://www.gojek.com/">Help Centre</a>
        <a href="https://www.gojek.com/">Join Us</a>
        <a href="https://www.gojek.com/">Safety</a>
      </div>
    {/if}
  </div>
  <div class="header__burger" on:click={click}>
    <Hamburger />
  </div>
</div>
