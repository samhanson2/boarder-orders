<script>
  import { stores } from "@sapper/app";
  const { session } = stores();

  session.cart = [];
</script>

<style>
  .title {
    font-size: 40px;
    padding: 10px;
    background-color: rgba(255, 255, 255, 0.5);
  }
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
  .button {
    display: block;
    margin: 20px;
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
    padding: 1px;
  }
</style>

<h1 class="title has-text-centered">Order Food</h1>
<div class="whitebox">
  <a
    href="./lookfood"
    onclick="body.style.backgroundColor = 'hsl(142, 85%, 38%, 0.5)';"
    class="button is-large is-success green">
    Green Flat
  </a>
</div>
<div class="whitebox">
  <a
    href="./lookfood"
    onclick="body.style.backgroundColor = 'hsla(204, 86%, 53%, 0.5)';"
    class="button is-large is-info blue">
    Blue Flat
  </a>
</div>
<div class="whitebox">
  <a
    href="./lookfood"
    onclick="body.style.backgroundColor = 'rgba(255, 140, 0, 0.8)';"
    class="button is-large orange">
    Orange Flat
  </a>
</div>
<div class="whitebox">
  <a
    href="./lookfood"
    onclick="body.style.backgroundColor = 'hsl(48, 100%, 67%, 0.8)';"
    class="button is-large is-warning yellow">
    Yellow Flat
  </a>
</div>
<div class="whitebox">
  <a
    href="./lookfood"
    onclick="document.body.style.backgroundColor = 'pink';"
    class="button is-large pink">
    Pink Flat
  </a>
</div>
