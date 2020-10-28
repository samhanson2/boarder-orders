<script>
  import { stores } from "@sapper/app";
  const { session } = stores();

  let cartItems = 0;

  import Fooditem from "./_components/Fooditem.svelte";
  import foodItems from "./foodItems";
  import Header from "./_components/Header.svelte";

  let title = "Food Order";
  // creates if not done already
  if (session.cart === undefined) {
    session.cart = [];
  }
</script>

<Header {title} bind:items={cartItems} />

<!-- Each foodItem print -->
{#each foodItems as item}
  <div>
    <Fooditem bind:items={cartItems} {...item} />
  </div>
{/each}
