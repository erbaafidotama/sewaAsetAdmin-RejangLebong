<script>
  import { DataTable } from "carbon-components-svelte";

  export let dataTable;
  export let headerTable;
</script>

<DataTable zebra radio headers={headerTable} rows={dataTable} />
