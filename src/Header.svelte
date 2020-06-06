<script>
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
  .header #left {
    display: flex;
  }
  .header__menu {
    display: none;
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
  @media (min-width: 720px) {
    .header__burger {
      display: none;
    }
    .header__menu {
      display: flex;
      margin-left: 32px;
      width: 42ch;
      justify-content: space-between;
      align-items: center;
    }
  }
</style>

<div class="header">
  <div id="left">
    <div class="header__brand" style="margin-left:{ml}px;">
      <img src="static/images/gojek-logo_normal.svg" alt />
    </div>
    <div class="header__menu">
      <a href="https://www.gojek.com/">About Us</a>
      <a href="https://www.gojek.com/">Services</a>
      <a href="https://www.gojek.com/">Blog</a>
      <a href="https://www.gojek.com/">Help Centre</a>
      <a href="https://www.gojek.com/">Join Us</a>
      <a href="https://www.gojek.com/">Safety</a>
    </div>
  </div>
  <div class="header__burger" on:click={click}>
    <Hamburger />
  </div>
</div>
