<script>
  export let w = 0;
  export let name = "";
  export let desc = "";
  export let items = [];
</script>

<style>
  .card {
    border-radius: 10px;
    box-shadow: var(--box-shadow);
    margin: 0 1ch 2ch 1ch;
    width: 189px;
  }
  .card img {
    margin: 1em 0;
  }
  .service__xscroll {
    display: flex;
    overflow-x: scroll;
    margin-bottom: 1em;
  }
  .service__xscroll a {
    display: inline-block;
  }
</style>

<div class="service" style="width:{w}px;">
  <div class="service__caption">
    <h3>{name}</h3>
    <p>{desc}</p>
  </div>
  <div class="service__xscroll">
    {#each items as i}
      <a href="https://www.gojek.com/{i}/">
        <div class="card">
          <img src="static/images/{name}/{i}_vertical.svg" alt />
        </div>
      </a>
    {/each}
  </div>
</div>
