<script>
  export let type = "submit";
</script>

<button {type}>
  <slot />
</button>

<style>
  button {
    cursor: pointer;
    border: none;
    transition: transform 0.1s ease;
    background-color: var(--dark-desaturated-blue);
    color: var(--pale-blue);
    width: 170px;
    height: 42px;
    border-radius: 21px;
  }

  button:active {
    transform: scale(0.95);
  }
</style>
