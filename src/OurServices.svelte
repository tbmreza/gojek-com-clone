<script>
  import Service from "./Service.svelte";

  const services = [
    {
      name: "Transport & Logistics",
      desc:
        "Moving something (or someone) from point A to point B? Our Gojek drivers in green jackets and helmets save your time, and energy.",
      items: ["goride", "gocar", "gosend", "gobox"]
    },
    {
      name: "Food & FMCG",
      desc:
        "Order food from a whole lotta restaurants, get medicines delivered in a jiffy, or fill your shopping cart from many a mart.",
      items: ["gofood", "gofoodfestival", "gomed", "gomart"]
    },
    {
      name: "Payments",
      desc:
        "From split the bills to donations, we make payments reliable, easy and delightful for our customers and merchants alike.",
      items: ["gopay", "gobills", "gopoints", "paylater", "gopulsa"]
    },
    {
      name: "Daily Needs",
      desc:
        "Those regular chores that call for your attention? We have all products under daily needs to make your life simpler and hassle-free.",
      items: ["golife", "gomassage", "goclean"]
    },
    {
      name: "News & Entertainment",
      desc:
        "Binge on your favourite series, book tickets to the next concert, organise celebrity events, and do much more. All your treasured digital content belong here.",
      items: ["goplay", "gotix"]
    },
    {
      name: "Business",
      desc: "Your business partner",
      items: ["gobiz"]
    }
  ];
</script>

<style>
  h2 {
    margin-bottom: 0;
  }
</style>

<h2>Our Services</h2>

{#each services as s}
  <Service name={s.name} desc={s.desc} items={s.items} />
{/each}
