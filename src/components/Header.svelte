<script>
  export let title;
  export let subTitle;
</script>

<header>
  <h1>{title}</h1>
  <h2>{subTitle}</h2>
</header>

<style>
  header {
    padding: 90px 0 65px;
    background: url("/images/pattern-circles.svg") center 65% no-repeat;
    text-align: center;
  }

  h1 {
    margin: 0;
    font-size: 20px;
    color: var(--dark-desaturated-blue);
  }

  h2 {
    margin: 5px auto 0;
    max-width: 170px;
    font-size: 13px;
    line-height: 1.75;
    font-weight: 600;
  }

  @media (min-width: 700px) {
    header {
      padding: 104px 0 88px;
      background-position: center 55%;
    }

    h1 {
      font-size: 28px;
    }

    h2 {
      max-width: 100%;
      font-size: 15px;
      margin-top: 9px;
    }
  }
</style>
