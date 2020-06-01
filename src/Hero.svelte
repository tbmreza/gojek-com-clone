<script>
  export let w = 0;
  import Carousel from "@beyonk/svelte-carousel";
</script>

<style>
  @media (min-width: 680px) {
    .slide-content {
      display: flex;
      justify-content: center;
      background-color: rgb(38 38 38);
    }
    img {
      height: 700px;
      width: auto;
    }
  }
</style>

<Carousel perPage={1} autoplay={5000} duration={800} draggable loop>
  <div class="slide-content">
    <img src="static/images/hero/covid_mobile.jpg" width="{w}px" alt />
  </div>
  <div class="slide-content">
    <img src="static/images/hero/ebadah_mobile.jpg" width="{w}px" alt />
  </div>
  <div class="slide-content">
    <img src="static/images/hero/kitabisa_mobile.jpg" width="{w}px" alt />
  </div>
</Carousel>
