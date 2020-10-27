<script>
  import { stores } from "@sapper/app";
  const { session } = stores();
  export let title = "";
  export let items;
  export let link = ".";
</script>

<style>
  /* style Bulma card of card, title, button*/
  .card {
    margin-bottom: 10px;
    background-color: rgba(255, 255, 255, 0.5);
  }
  .title {
    padding: 20px;
    text-align: center;
  }
  .button {
    font-size: 25px;
    font-weight: bold;
  }
</style>

<!-- Bulma Card -->
<div class="card">
  <div class="card-content">
    <div class="media">
      <div class="media-left">
        <a href={link} class="button">Back</a>
      </div>
      <div class="media-content">
        <p class="title">{title}</p>
      </div>
      <a href="./cartitems" class="button cart">cart {items}</a>
    </div>
  </div>
</div>
