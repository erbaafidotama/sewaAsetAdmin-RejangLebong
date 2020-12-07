<script>
  import {
    AppBar,
    Button,
    Icon,
    Menu,
    ListItem,
    Overlay,
    NavigationDrawer,
    List,
    Divider,
  } from "svelte-materialify";
  import {push} from 'svelte-spa-router'

  let active = false;

  function close() {
    active = false;
  }
  function open() {
    active = true;
  }
</script>

<style>
  .img-svg {
    margin-right: 2em;
    margin-left: 1em;
  }
  .title-menu {
      text-align: center;
  }
</style>

<AppBar>
  <div slot="icon">
    <Button fab depressed on:click={open}>
      <svg
        xmlns="http://www.w3.org/2000/svg"
        viewBox="0 0 24 24"
        width="24"
        height="24"><path fill="none" d="M0 0h24v24H0z" />
        <path d="M3 4h18v2H3V4zm0 7h18v2H3v-2zm0 7h18v2H3v-2z" /></svg>
    </Button>
  </div>
  <span slot="title">Si-Tekur Admin</span>
</AppBar>
<NavigationDrawer absolute {active}>
  <List>
    <h5 class="title-menu">Si-Tekur Admin</h5>
    <Divider />
    <ListItem on:click={() => push('/user')}>
      <span slot="prepend">
        <svg
          class="img-svg"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          width="24"
          height="24"><path fill="none" d="M0 0h24v24H0z" />
          <path
            d="M20 22H4v-2a5 5 0 0 1 5-5h6a5 5 0 0 1 5 5v2zm-8-9a6 6 0 1 1 0-12 6 6 0 0 1 0 12z" /></svg>
      </span>
      Master User
    </ListItem>
    <ListItem on:click={() => push('/item')}>
      <span slot="prepend">
        <svg
          class="img-svg"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          width="24"
          height="24"><path fill="none" d="M0 0h24v24H0z" />
          <path
            d="M3 10H2V4.003C2 3.449 2.455 3 2.992 3h18.016A.99.99 0 0 1 22 4.003V10h-1v10.001a.996.996 0 0 1-.993.999H3.993A.996.996 0 0 1 3 20.001V10zm16 0H5v9h14v-9zM4 5v3h16V5H4zm5 7h6v2H9v-2z" /></svg>
      </span>
      Master Item
    </ListItem>
    <Divider />
    <ListItem on:click={() => push('/transaction')}>
      <span slot="prepend">
        <svg
          class="img-svg"
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 24 24"
          width="24"
          height="24"><path fill="none" d="M0 0h24v24H0z" />
          <path
            d="M19.375 15.103A8.001 8.001 0 0 0 8.03 5.053l-.992-1.737A9.996 9.996 0 0 1 17 3.34c4.49 2.592 6.21 8.142 4.117 12.77l1.342.774-4.165 2.214-.165-4.714 1.246.719zM4.625 8.897a8.001 8.001 0 0 0 11.345 10.05l.992 1.737A9.996 9.996 0 0 1 7 20.66C2.51 18.068.79 12.518 2.883 7.89L1.54 7.117l4.165-2.214.165 4.714-1.246-.719zM8.5 14H14a.5.5 0 1 0 0-1h-4a2.5 2.5 0 1 1 0-5h1V7h2v1h2.5v2H10a.5.5 0 1 0 0 1h4a2.5 2.5 0 1 1 0 5h-1v1h-2v-1H8.5v-2z" /></svg>
      </span>
      Transactions
    </ListItem>
  </List>
</NavigationDrawer>
<Overlay index={1} {active} on:click={close} absolute />
