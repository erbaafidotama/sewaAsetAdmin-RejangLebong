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
    Select,
    Textarea,
  } from "svelte-materialify";

  import Table from "../../components/Table.svelte";

  const dataTable = [
    {
      id: 1,
      nik: "123456789",
      item: "kursi",
      rent_amount: 50,
      description: "kursi ini dipinjam 50",
    },
  ];

  const headerTable = [
    {
      key: "nik",
      value: "NIK",
    },
    {
      key: "item",
      value: "Item",
    },
    {
      key: "rent_amount",
      value: "Rent Amount",
    },
    {
      key: "description",
      value: "Description",
    },
  ];

  const items = [
    { name: "Kursi", value: "Kursi" },
    { name: "Ruangan", value: "Ruangan" },
  ];
  const people = [
    { name: "Kursi", value: "Kursi" },
    { name: "Ruangan", value: "Ruangan" },
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
  <h2>Transaction</h2>
  <ButtonGroup>
    <ButtonGroupItem>Edit</ButtonGroupItem>
    <ButtonGroupItem on:click={openModal}>New</ButtonGroupItem>
  </ButtonGroup>
</div>

<Table {dataTable} {headerTable} />

<Dialog class="pa-4" bind:active>
  <h4>Create Transaction</h4>
  <Divider />
  <Row>
    <Col>
      <Select outlined dense items={people}>NIK</Select>
    </Col>
  </Row>
  <Row>
    <Col>
      <Select outlined dense {items}>Item</Select>
    </Col>
  </Row>
  <Row>
    <Col>
      <TextField dense outlined type="number">Rent Amount</TextField>
    </Col>
  </Row>
  <Row>
    <Col>
      <Textarea dense outlined>Description</Textarea>
    </Col>
  </Row>
  <Divider />
  <div class="float-right">
    <Button on:click={closeModal}>Close</Button>
    <Button>Save</Button>
  </div>
</Dialog>
