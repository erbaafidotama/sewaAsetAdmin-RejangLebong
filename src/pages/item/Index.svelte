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
    Textarea,
  } from "svelte-materialify";

  import Table from "../../components/Table.svelte";

  const dataTable = [
    
  ];

  const headerTable = [
    {
      key: "item_name",
      value: "Item Name",
    },
    {
      key: "price",
      value: "Price",
    },
    {
      key: "quantity",
      value: "Quantity",
    },
    {
      key: "description",
      value: "Description",
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
  <h2>Master Item</h2>
  <ButtonGroup>
    <ButtonGroupItem>Edit</ButtonGroupItem>
    <ButtonGroupItem on:click={openModal}>New</ButtonGroupItem>
  </ButtonGroup>
</div>

<Table {dataTable} {headerTable} />

<Dialog class="pa-4" bind:active>
  <h4>Create Item</h4>
  <Divider />
  <Row>
    <Col>
      <TextField dense outlined>Item Name</TextField>
    </Col>
  </Row>
  <Row>
    <Col>
      <TextField dense outlined type="number">Price</TextField>
    </Col>
  </Row>
  <Row>
    <Col>
      <TextField dense outlined type="number">Quantity</TextField>
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
