<script>
  export let amount;
  export let period;
</script>

<div class="price">
  <span class="price-amount">${amount.toFixed(2)}</span>
  <span class="price-period">/ {period}</span>
</div>

<style>
  .price {
    display: flex;
    align-items: center;
    gap: 10px;

    order: 3;
  }

  .price-amount {
    font-weight: 800;
    font-size: 32px;
    color: var(--dark-desaturated-blue);
  }

  .price-period {
    font-size: 13px;
  }

  @media (min-width: 700px) {
    .price {
      order: 2;
    }

    .price-amount {
      font-size: 38px;
    }

    .price-period {
      font-size: 16px;
    }
  }
</style>
