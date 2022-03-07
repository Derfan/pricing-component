<script>
  export let value;

  $: innerWidth = 0;

  function onChange(event) {
    value = event.target.checked;
  }
</script>

<svelte:window bind:innerWidth />

<div class="switch">
  <p class="value">Monthly Billing</p>

  <label class="label">
    <input type="checkbox" name="period" on:change|preventDefault={onChange} />
    <span class="slider" />
  </label>

  <p class="value">
    Yearly Billing
    <span>{innerWidth < 700 ? "-25%" : "25% discount"}</span>
  </p>
</div>

<style>
  .switch {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;

    order: 4;
  }

  .value {
    margin: 0;
    position: relative;
    font-size: 12px;
  }

  .value > span {
    position: absolute;
    right: -45px;
    top: 50%;
    font-size: 10px;
    font-weight: 800;
    border-radius: 10px;
    transform: translateY(-50%);
    padding: 3px 8px;
    color: var(--light-red);
    background-color: #fdefeb;
  }

  .label {
    position: relative;
    display: inline-block;
    width: 43px;
    height: 22px;
  }

  .label > input {
    opacity: 0;
    width: 0;
    height: 0;
  }

  .slider {
    position: absolute;
    cursor: pointer;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    background-color: #ccc;
    border-radius: 15px;
    transition: 0.4s;
  }

  .slider::before {
    position: absolute;
    content: "";
    height: 14px;
    width: 14px;
    left: 4px;
    bottom: 4px;
    background-color: white;
    transition: 0.4s;
    border-radius: 50%;
  }

  input:checked + .slider {
    background-color: var(--strong-cyan);
  }

  input:focus + .slider {
    box-shadow: 0 0 1px var(--strong-cyan);
  }

  input:checked + .slider:before {
    transform: translateX(22px);
  }

  @media (min-width: 700px) {
    .switch {
      gap: 16px;
    }

    .value > span {
      right: -90px;
    }
  }
</style>
