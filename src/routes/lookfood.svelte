<script>
  import { stores } from "@sapper/app";
  const { session } = stores();

  session.cart = [];

  import Fooditem from "./_components/Fooditem.svelte";
  import foodItems from "./foodItems";
  import Header from "./_components/Header.svelte";
  let title ="Food Order"
</script>

<Header {title} />

{#each foodItems as item}
  <div>
    <Fooditem {...item} />
  </div>
{/each}
