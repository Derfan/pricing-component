<script>
  export let author;
</script>

<div class="attribution">
  Challenge by <a
    href="https://www.frontendmentor.io?ref=challenge"
    target="_blank">Frontend Mentor</a
  >. Coded by
  <a href={author.link}>{author.name}</a>.
</div>

<style>
  .attribution {
    font-size: 11px;
    text-align: center;
    margin-top: 65px;
  }
  .attribution a {
    color: hsl(228, 45%, 44%);
  }
</style>
