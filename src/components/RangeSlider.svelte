<script>
  import RangeSlider from "svelte-range-slider-pips";

  export let settings;
  export let value;

  function onChange(event) {
    value = event.detail.value;
  }
</script>

<RangeSlider
  id="color-pips"
  range="min"
  values={[value]}
  {...settings}
  on:change={onChange}
/>

<style>
  :global(.rangeSlider) {
    --range-slider: hsl(223, 6%, 97%);
    --range-range-inactive: hsl(174, 77%, 80%);
    --range-handle-inactive: hsl(174, 86%, 45%);
    --range-range: hsl(174, 86%, 45%);
    --range-handle: hsl(174, 77%, 80%);
    --range-handle-focus: hsl(174, 86%, 45%);

    cursor: pointer;
    width: 100%;
    margin: 0 !important;

    order: 2;
  }

  @media (min-width: 700px) {
    :global(.rangeSlider) {
      order: 3;
    }
  }

  :global(.rangeSlider) > :global(.rangeHandle) {
    width: 40px !important;
    height: 40px !important;
  }

  :global(.rangeSlider) > :global(.rangeHandle.active) {
    cursor: grabbing;
  }

  :global(.rangeSlider) > :global(.rangeHandle) > :global(.rangeNub) {
    transform: rotate(0deg) !important;
    background-image: url("/images/icon-slider.svg");
    background-position: center center;
    background-repeat: no-repeat;
  }
</style>
