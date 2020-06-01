<script>
  import About from "./About.svelte";
  import Snackbar from "./Snackbar.svelte";
  import OurServices from "./OurServices.svelte";
  import Hero from "./Hero.svelte";
  import Carousel from "@beyonk/svelte-carousel";
  import Header from "./Header.svelte";
  import Modal from "modal-overlay";

  const fraction = 0.8;
  let w;
  let open = false;
  let show = false;
</script>

<style>
  #main {
    display: flex;
    flex-direction: column;
  }
  #main > div {
    margin-left: auto;
    margin-right: auto;
    margin-bottom: 16px;
  }
  #install-app {
    position: sticky;
    bottom: 0;
  }
  .header__menu--modal {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .header__menu--modal > a {
    margin: 1em 0;
  }
</style>

<svelte:window bind:innerWidth={w} />

<div id="main">
  <Header {w} ml={(w * (1 - fraction)) / 2} bind:show />
  <Hero {w} />
  <div style="margin-top:16px;">
    <About w={w * fraction} />
  </div>
  <div>
    <OurServices w={w * fraction} />
  </div>
  <div id="install-app">
    <Snackbar w={w * 0.95} />
  </div>
</div>

{#if show}
  <Modal>
    <div class="header__menu--modal">
      <a href="https://www.gojek.com/">About Us</a>
      <a href="https://www.gojek.com/">Services</a>
      <a href="https://www.gojek.com/">Blog</a>
      <a href="https://www.gojek.com/">Help Centre</a>
      <a href="https://www.gojek.com/">Join Us</a>
      <a href="https://www.gojek.com/">Safety</a>
    </div>
  </Modal>
{/if}
