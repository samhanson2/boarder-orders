<script>
  import { stores } from "@sapper/app";
  const { session } = stores();

  import Header from "./_components/Header.svelte";
  import Fooditem from "./_components/Fooditem.svelte";
  let title = "Cart";
  let link = "./stylefood";

  /* crating array if session.cart is undefined */
  if (session.cart === undefined) {
    session.cart = [];
  }

  /* removing items */
  function removeItem(index) {
    session.cart = [
      ...session.cart.slice(0, index),
      ...session.cart.slice(index + 1)
    ];
  }
  /* Storing items */
  function saveDataToLocal() {
    let order = {
      cart: session.cart
    };
    db.collection("orders")
      .doc(session.flat)
      .set(order);
  }

  /* Get items from storing */
  async function getDataFromLocal() {
    let orderDoc = await db
      .collection("orders")
      .doc(session.flat)
      .get();
    let order = orderDoc.data();
    session.cart = order.cart;
  }
</script>

<style>
  .card {
    margin-top: 20px;
    margin-bottom: 20px;
  }
  .media-right {
    margin-left: 50px;
  }
</style>

<Header {link} {title} items={session.cart.length} />

<table style="width:100%">
  <tr>
    <th class="title">Item Name</th>
  </tr>
  <tr>
    <td>
      <!-- loop for each item in session.cart prints each item as card -->
      {#each session.cart as cartItem, index}
        <div class="card">
          <div class="card-content">
            <div class="media">
              <div class="media-left">
                <p class="title">{cartItem.name}</p>
                <p class="subtitle">{cartItem.desc}</p>
              </div>
              <div class="media-content">
                <p class="title">${cartItem.num}</p>
              </div>
              <div class="media-right">
                <button
                  class="button"
                  on:click={() => {
                    removeItem(index);
                  }}>
                  Remove
                </button>
              </div>
            </div>
          </div>
        </div>
      {/each}
      <button class="button" on:click={saveDataToLocal}>
        Remember my order
      </button>
      <button class="button" on:click={getDataFromLocal}>Get last order</button>
    </td>
  </tr>
</table>
