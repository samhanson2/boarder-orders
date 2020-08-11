<script>
  import { stores } from "@sapper/app";
  const { session } = stores();

  import Header from "./_components/Header.svelte";
  import Fooditem from "./_components/Fooditem.svelte";
  let title = "Cart";
</script>

<style>
  .card {
    margin-top: 20px;
  }
</style>

<Header {title} />

<table style="width:100%">
  <tr>
    <th class="title">Item Name</th>
  </tr>
  <tr>
    <td>
      {#if session.cart}
        {#each session.cart as cartItem}
          <div class="card">
            <div class="card-content">
              <div class="media">
                <div class="media-left">
                  <p class="title">{cartItem}</p>
                </div>
                <div class="media-content">
                  <p class="title">1</p>
                </div>
                <!-- <button class="button is-right">Remove</button> -->
              </div>
            </div>
          </div>
        {/each}
      {/if}
    </td>
  </tr>
</table>
<!-- on:click={remove} -->
