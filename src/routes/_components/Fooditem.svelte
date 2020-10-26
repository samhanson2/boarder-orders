<script>
  import { stores } from "@sapper/app";
  const { session } = stores();

  export let name = "No name";
  export let desc = "No description";
  export let src = "https://bulma.io/images/placeholders/96x96.png";
  export let num = 0;
  export let items = 0;
  export let alt = "placeholder";

  /* adds items to an array */
  function addFood() {
    session.cart = [...session.cart, { name: name, desc: desc, num: num }];
    items += 1;
  }
</script>

<style>
/* style bulma card */
  .card {
    margin-bottom: 10px;
  }
  div {
    background-color: antiquewhite;
  }
  .button {
    font-size: 25px;
    font-weight: bold;
  }
  .subtitle {
    font-size: 28px;
    color: black;
  }
</style>
<!-- bulma card -->
<div class="card">
  <div class="card-content">
    <div class="media">
      <div class="media-left">
        <figure class="image is-96x96">
          <img {src} alt="{alt}" />
        </figure>
      </div>
      <div class="media-content">
        <p class="title">{name}</p>
        <p class="subtitle">{desc}</p>
      </div>
      <div class="media-right">
        <p class="subtitle">${num}</p>
        <!-- add to cart button -->
        <button class="button" on:click={addFood}>Add to cart</button>
      </div>
    </div>
  </div>
</div>
