<script>
  import { stores } from '@sapper/app'
  const { session } = stores()

  export let name = "No name";
  export let desc = "No description";
  export let src = "https://bulma.io/images/placeholders/96x96.png";

  function addFood() {
    session.cart = [...session.cart, name];
  }
</script>

<style>
    .card {
    margin-bottom: 10px;
  }
  div {
    background-color: antiquewhite;
  }
</style>

<div class="card">
  <div class="card-content">
    <div class="media">
      <div class="media-left">
        <figure class="image is-96x96">
          <img {src} alt="Placeholder" />
          <!-- <img src="https://bulma.io/images/placeholders/96x96.png" alt="Placeholder"> -->
        </figure>
      </div>
      <div class="media-content">
        <p class="title">{name}</p>
        <p class="subtitle">{desc}</p>
      </div>
      <button class="button is-right" on:click={addFood}>Add to cart</button>
    </div>
  </div>
</div>

