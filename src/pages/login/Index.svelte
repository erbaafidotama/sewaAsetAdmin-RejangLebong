<script>
  import {
    Card,
    CardText,
    CardActions,
    Button,
    Divider,
    TextField,
  } from "svelte-materialify";
  import { push } from "svelte-spa-router";

  function doLogin() {
    sessionStorage.setItem("loged", true);
    push("/user");
    // loged = true;
  }
</script>

<style>
  .box-login {
    position: fixed;
    top: 50%;
    left: 50%;
    -webkit-transform: translate(-50%, -50%);
    transform: translate(-50%, -50%);
  }
</style>

<div class="d-flex justify-center box-login">
  <Card outlined shaped raised>
    <div class="pl-4 pr-4 pt-3">
      <p class="text-h3 text-center mb-2">Login</p>
      <br />
      <Divider />
    </div>

    <CardText>
      <TextField>
        <div slot="prepend-outer">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
            width="24"
            height="24"><path fill="none" d="M0 0h24v24H0z" />
            <path
              d="M12 17c3.662 0 6.865 1.575 8.607 3.925l-1.842.871C17.347 20.116 14.847 19 12 19c-2.847 0-5.347 1.116-6.765 2.796l-1.841-.872C5.136 18.574 8.338 17 12 17zm0-15a5 5 0 0 1 5 5v3a5 5 0 0 1-4.783 4.995L12 15a5 5 0 0 1-5-5V7a5 5 0 0 1 4.783-4.995L12 2zm0 2a3 3 0 0 0-2.995 2.824L9 7v3a3 3 0 0 0 5.995.176L15 10V7a3 3 0 0 0-3-3z" /></svg>
        </div>
        NIK
      </TextField>
      <br />
      <TextField type="date">
        <div slot="prepend-outer">
          <svg
            xmlns="http://www.w3.org/2000/svg"
            viewBox="0 0 24 24"
            width="24"
            height="24"><path fill="none" d="M0 0h24v24H0z" />
            <svg
              xmlns="http://www.w3.org/2000/svg"
              viewBox="0 0 24 24"
              width="24"
              height="24"><path fill="none" d="M0 0h24v24H0z" />
              <path
                d="M12 22C6.477 22 2 17.523 2 12S6.477 2 12 2s10 4.477 10 10-4.477 10-10 10zm0-2a8 8 0 1 0 0-16 8 8 0 0 0 0 16zm1-8h4v2h-6V7h2v5z" /></svg>
          </svg>
        </div>
        Birthdate
      </TextField>
    </CardText>
    <CardActions class="justify-center">
      <Button rounded class="primary-color" on:click={doLogin}>Login</Button>
    </CardActions>
  </Card>
</div>
