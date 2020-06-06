<script>
  import About from "./About.svelte";
  import Snackbar from "./Snackbar.svelte";
  import OurServices from "./OurServices.svelte";
  import Hero from "./Hero.svelte";
  import Carousel from "@beyonk/svelte-carousel";
  import Header from "./Header.svelte";
  import Modal from "modal-overlay";
  import Times from "./TimesIcon.svelte";

  const fraction = 0.8;
  let w;
  let show = false;

  $: mobile = w < 650;

  function closeSnackbar() {
    mobile = false;
  }
</script>

<style>
  #main {
    display: flex;
    flex-direction: column;
  }
  #main > div {
    margin: 0 auto;
    margin-bottom: 16px;
    /* margin: auto; */
  }

  .header__menu--modal {
    display: flex;
    flex-direction: column;
    align-items: center;
  }
  .header__menu--modal > a {
    margin: 1em 0;
  }

  /* snackbar */
  .install-app {
    display: flex;
    align-items: center;
    justify-content: space-between;
  }
  .install-app #left {
    display: flex;
    align-items: center;
  }
  .install-app__logo > img {
    margin: 0 1em;
    width: 64px;
  }
  .install-app__caption > p {
    font-size: 10px;
  }
  .install-app__caption > * {
    margin: 0;
  }
  .pointer:hover {
    cursor: pointer;
  }
</style>

<svelte:window bind:innerWidth={w} />

<Header ml={(w * (1 - fraction)) / 2} bind:show />
<Hero {w} />
<div id="main">
  <div style="margin-top:16px;">
    <About w={w * fraction} />
  </div>
  <div>
    <OurServices />
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

{#if mobile}
  <Snackbar>
    <div class="install-app">
      <div id="left">
        <div class="install-app__x pointer" on:click={closeSnackbar}>
          <Times />
        </div>
        <div class="install-app__logo">
          <img alt="Gojek App" src="static/images/Gojek_ID2x.jpg" />
        </div>
        <div class="install-app__caption">
          <h5>Gojek App</h5>
          <p>One app for every need</p>
        </div>
      </div>
      <a href="https://www.gojek.com/">
        <button class="pointer">Open</button>
      </a>
    </div>
  </Snackbar>
{/if}
