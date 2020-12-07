<script>
  import {
    Button,
    ButtonGroup,
    ButtonGroupItem,
    Col,
    Dialog,
    Divider,
    Row,
    TextField,
  } from "svelte-materialify";

  import Table from "../../components/Table.svelte";

  const dataTable = [
    {
      id: 1,
      nik: "123456789",
      email: "admin@gmail.com",
      username: "admin12345",
      full_name: "admin",
    },
  ];

  const headerTable = [
    {
      key: "nik",
      value: "NIK",
    },
    {
      key: "email",
      value: "Email",
    },
    {
      key: "username",
      value: "Username",
    },
    {
      key: "full_name",
      value: "Full Name",
    },
  ];

  let active = false;
  function openModal() {
    active = true;
  }
  function closeModal() {
    active = false;
  }
</script>

<div class="d-flex justify-space-between">
  <h2>Master User</h2>
  <ButtonGroup>
    <ButtonGroupItem>Edit</ButtonGroupItem>
    <ButtonGroupItem on:click={openModal}>New</ButtonGroupItem>
  </ButtonGroup>
</div>

<Table {dataTable} {headerTable} />

<Dialog class="pa-4" bind:active>
  <h4>Create User</h4>
  <Divider />
  <Row>
    <Col>
      <TextField dense outlined>NIK</TextField>
    </Col>
    <Col>
      <TextField dense outlined type="password">Password</TextField>
    </Col>
  </Row>
  <Row>
    <Col>
      <TextField dense outlined>Email</TextField>
    </Col>
  </Row>
  <Row>
    <Col>
      <TextField dense outlined>Username</TextField>
    </Col>
  </Row>
  <Row>
    <Col>
      <TextField dense outlined>Fullname</TextField>
    </Col>
  </Row>
  <Divider />
  <div class="float-right">
    <Button on:click={closeModal}>Close</Button>
    <Button>Save</Button>
  </div>
</Dialog>
