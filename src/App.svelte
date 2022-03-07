<script>
  import Header from "./components/Header.svelte";
  import PricingCard from "./components/PricingCard.svelte";
  import Footer from "./components/Footer.svelte";
</script>

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

  @media (min-width: 700px) {
    main {
      margin: 0 auto;
      width: 540px;
    }
  }
</style>
