<script>
  // import Fooditem from "./_components/Fooditem.svelte";
  // import foodItems from "./foodItems";
</script>

<style>
  :global(body) {
    background-color: #ecb865;
  }
  .title {
    padding: 10px;
    background-color: rgba(255, 255, 255, 0.5);
  }
  .orange {
    color: white;
    background-color: darkorange;
  }
  .pink {
    color: white;
    background-color: hotpink;
  }
  .yellow {
    color: white;
  }
  .button {
    display: block;
    margin: 20px;
  }
  .whitebox {
    background-color: white;
    border-radius: 5px;
    margin: 20px;
    padding: 1px;
  }
</style>

<svelte:head>
  <title>Food Order</title>
  <meta name="viewport" content="width=device-width, initial-scale=0.5" />
</svelte:head>

<h1 class="title has-text-centered">Order Food</h1>
<div class="whitebox">
  <a href="./lookfood" class="button is-medium is-success green">Green Flat</a>
</div>
<div class="whitebox">
  <a href="./lookfood" class="button is-medium is-info blue">Blue Flat</a>
</div>
<div class="whitebox">
  <a href="./lookfood" class="button is-medium orange">Orange Flat</a>
</div>
<div class="whitebox">
  <a href="./lookfood" class="button is-medium is-warning yellow">
    Yellow Flat
  </a>
</div>
<div class="whitebox">
  <a href="./lookfood" class="button is-medium pink">Pink Flat</a>
</div>
