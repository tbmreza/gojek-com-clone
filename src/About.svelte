<script>
  export let w = 0;
  import ArrowRightIcon from "./ArrowRightIcon.svelte";
</script>

<style>
  .about {
    --more-width: 12ch;
    margin: 0;
    display: flex;
    justify-content: center;
    flex-direction: column;
  }
  .about__pic {
    display: flex;
    justify-content: center;
  }
  .about__pic > img {
    max-width: 700px;
    border-radius: 16px;
  }
  .about__caption {
    margin: auto;
  }

  .about__caption > a {
    text-decoration: none;
  }
  .about__more {
    width: var(--more-width);
    color: var(--brand-main);
  }
  .about__more__flex {
    display: flex;
    justify-content: space-between;
  }
  .about__more__flex > .arrow {
    display: inline-block;
  }
  .about__more__bar > div {
    height: 2px;
    width: 0;
  }
  .about__more:hover .about__more__bar > div {
    background-color: var(--brand-main);
    width: var(--more-width);
    transition: width 0.3s;
  }

  @media (min-width: 1024px) {
    .about {
      flex-direction: row;
    }
    .about__pic > img {
      max-width: 500px;
    }
    .about__caption {
      margin-left: 32px;
    }
    .about__pic {
      justify-content: space-between;
    }
  }
</style>

<div class="about" style="width:{w}px;">
  <div class="about__pic">
    <img src="static/images/about.webp" alt />
  </div>
  <div class="about__caption">
    <h2>About Yayasan Anak Bangsa Bisa</h2>
    <p>
      Yayasan Anak Bangsa Bisa (YABB) is a non-profit organization founded by
      Gojek to advance equal opportunities and help build more sustainable
      livelihoods for societies who rely on daily income
    </p>
    <a href="https://www.gojek.com/">
      <div class="about__more">
        <div class="about__more__flex">
          <span>Find Out Here</span>
          <div class="arrow">
            <ArrowRightIcon />
          </div>
        </div>
        <div class="about__more__bar">
          <div />
        </div>
      </div>
    </a>
  </div>
</div>
