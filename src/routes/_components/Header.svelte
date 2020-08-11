<script>
  import { stores } from "@sapper/app";
  const { session } = stores();
  export let title = "";
</script>

<style>
  .card {
    margin-bottom: 10px;
    background-color: rgba(255, 255, 255, 0.5);
  }
  .title {
    padding: 10px;
    text-align: center;
  }
  
</style>

<div class="card">
  <div class="card-content">
    <div class="media">
      <div class="media-left">
        <a href="." class="button">Back</a>
      </div>
      <div class="media-content">
        <p class="title">{title}</p>
      </div>
      <a href="./cartitems" class="button cart">
        cart
        {#if session.cart}
         {session.cart.length}
        {/if}
      </a>
    </div>
  </div>
</div>
