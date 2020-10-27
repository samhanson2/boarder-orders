<script>
  import { stores } from "@sapper/app";
  import { goto } from "@sapper/app";

  // creates session.cart
  const { session } = stores();
  session.cart = [];

  // function for buttons to go to next page
  function nameAndGo(flat) {
    session.flat = flat;
    goto("./stylefood");
  }
</script>

<style>
  /* styles title */
  .title {
    font-size: 40px;
    padding: 10px;
    background-color: rgba(255, 255, 255, 0.5);
  }
  /* colours flat buttons */
  .orange {
    color: white;
    background-color: rgba(255, 140, 0, 0.746);
  }
  .pink {
    color: white;
    background-color: hotpink;
  }
  .yellow {
    color: white;
  }
  /* styles buttons */
  .button {
    display: block;
    font-size: 38px;
    -webkit-text-stroke: 0.7px black;
    transition-duration: 0.1s;
    font-weight: bold;
  }
  .button:hover {
    color: black;
  }
  .whitebox {
    background-color: white;
    border-radius: 5px;
    margin: 10px;
    padding: 20px;
  }
</style>

<h1 class="title has-text-centered">Order Food</h1>
<!-- coloured flat buttons for each flat  -->
<div class="whitebox">
  <button
    onclick="body.style.backgroundColor = 'hsl(142, 85%, 38%, 0.5)';"
    on:click={() => {
      nameAndGo('Green');
    }}
    class="button is-fullwidth is-success green">
    Green Flat
  </button>
</div>
<div class="whitebox">
  <button
    onclick="body.style.backgroundColor = 'hsla(204, 86%, 53%, 0.5)';"
    on:click={() => {
      nameAndGo('Blue');
    }}
    class="button is-fullwidth is-info blue">
    Blue Flat
  </button>
</div>
<div class="whitebox">
  <button
    onclick="body.style.backgroundColor = 'rgba(255, 140, 0, 0.7)';"
    on:click={() => {
      nameAndGo('Orange');
    }}
    class="button is-fullwidth orange">
    Orange Flat
  </button>
</div>
<div class="whitebox">
  <button
    onclick="body.style.backgroundColor = 'hsl(48, 100%, 67%, 0.8)';"
    on:click={() => {
      nameAndGo('Yellow');
    }}
    class="button is-fullwidth is-warning yellow">
    Yellow Flat
  </button>
</div>
<div class="whitebox">
  <button
    onclick="document.body.style.backgroundColor = 'pink';"
    on:click={() => {
      nameAndGo('Pink');
    }}
    class="button is-fullwidth pink">
    Pink Flat
  </button>
</div>
