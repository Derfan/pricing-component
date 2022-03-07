<script>
  export let icon = "images/icon-check.svg";
  export let items;
</script>

<ul>
  {#each items as item}
    <li>
      {#if icon}
        <img src={icon} alt="icon" />
      {/if}
      <span>{item}</span>
    </li>
  {/each}
</ul>

<style>
  ul {
    margin: 0;
    padding: 0;
    list-style: none;

    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 10px;
  }

  li {
    display: flex;
    align-items: center;
  }

  img {
    margin-right: 14px;
  }

  span {
    font-size: 12px;
  }

  @media (min-width: 700px) {
    ul {
      align-items: flex-start;
    }
  }
</style>
