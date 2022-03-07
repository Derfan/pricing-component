<script>
  import Header from "./components/Header.svelte";
  import PricingCard from "./components/PricingCard.svelte";
  import Footer from "./components/Footer.svelte";
</script>

<img class="bg-pattern" src="images/bg-pattern.svg" alt="bg-pattern" />

<Header
  title="Simple, traffic-based pricing"
  subTitle="Sign-up for our 30-day trial. No credit card required."
/>

<main>
  <PricingCard />
</main>

<Footer />

<style>
  main {
    flex: 1 0 auto;
    padding: 0 24px;
  }

  .bg-pattern {
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    z-index: -1;
  }

  @media (min-width: 700px) {
    main {
      margin: 0 auto;
      width: 540px;
    }
  }
</style>
