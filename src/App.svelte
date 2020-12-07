<script>
  import Router from "svelte-spa-router";
  import { MaterialApp } from "svelte-materialify";

  import Appbar from "./components/Appbar.svelte";
  import Login from "./pages/login/Index.svelte";
  import User from "./pages/user/Index.svelte";
  import Item from "./pages/item/Index.svelte";
  import Transaction from "./pages/transaction/Index.svelte";

  let theme = "light";

  const routes = {
    // Exact path
    "/": Login,
    "/user": User,
    "/item": Item,
    "/transaction": Transaction,
  };

  const statusLogin = true;
  console.log(statusLogin);
</script>

<style>
  .app-container {
    margin-top: 10px;
  }
</style>

<MaterialApp {theme}>
  {#if statusLogin === true}
    <Appbar />
    <div class="container app-container">
      <Router {routes} />
    </div>
  {:else}
    <Router {routes} />
  {/if}
</MaterialApp>

<!-- <MaterialApp {theme}>
  <Appbar />
  <div class="container app-container">
    <Router {routes} />
  </div>
</MaterialApp> -->
