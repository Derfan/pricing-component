<script>
  import RangeSlider from "./RangeSlider.svelte";
  import InputSwitch from "./InputSwitch.svelte";
  import PriceBlock from "./PriceBlock.svelte";
  import List from "./List.svelte";
  import Button from "./Button.svelte";

  const BASE_PRICE = 0.16;

  $: pageviews = 100;
  $: isYearlyPrice = false;
  $: period = isYearlyPrice ? "year" : "month";
  $: amount = isYearlyPrice
    ? pageviews * BASE_PRICE * 0.75
    : pageviews * BASE_PRICE;

  function submitHandler() {
    console.log("form data:", { pageviews: pageviews * 1000, period });
  }
</script>

<form class="card" on:submit|preventDefault={submitHandler}>
  <div class="card-top">
    <h3 class="pageviews">{pageviews}K Pageviews</h3>

    <RangeSlider
      settings={{ min: 5, max: 200, step: 5 }}
      bind:value={pageviews}
    />

    <PriceBlock {amount} {period} />

    <InputSwitch bind:value={isYearlyPrice} />
  </div>

  <div class="card-bottom">
    <List
      items={["Unlimited websites", "100% data ownership", "Email reports"]}
    />

    <Button>Start my trial</Button>
  </div>
</form>

<style>
  .card {
    box-shadow: 0 1px 3px rgba(0, 0, 0, 0.12), 0 1px 2px rgba(0, 0, 0, 0.24);
    border-radius: 10px;
    background-color: var(--white);
  }

  .card-top {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 40px;
    padding: 35px 25px 38px;
    border-bottom: 1px solid hsl(233, 4%, 97%);
  }

  .pageviews {
    margin: 0;
    font-size: 12px;
    text-transform: uppercase;
    letter-spacing: 2px;

    order: 1;
  }

  .card-bottom {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 30px;
    padding: 25px 25px 30px;
  }

  @media (min-width: 700px) {
    .card-top {
      flex-direction: row;
      flex-wrap: wrap;
      justify-content: center;
      gap: 48px;
      padding: 42px 45px;
    }

    .pageviews {
      flex: 1 1 auto;
      font-size: 14px;
    }

    .card-bottom {
      flex-direction: row;
      justify-content: space-between;
      padding: 33px 44px;
    }
  }
</style>
