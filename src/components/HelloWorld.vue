<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1 style="display: inline-block">Fixed Header Table</h1>
    <h4 style="display: inline-block"> ...with hidden scroll bar</h4>

    <b-container fluid class="table-container">
      <b-table
        show-empty
        striped 
        hover
        small="small"
        stacked="md"
        :items="items" 
        :fields="fields" 
        caption-top
      >
        <template slot="table-caption">Fixed header table with hidden scroll bar.</template>
      </b-table>
    </b-container>

  </div>
</template>

<script>
import jsonData from './data.json'

export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  data() {
    return {
      fields: ['first_name', 'last_name', 'age'],
      // Data generated from https://www.json-generator.com/
      items: jsonData
    }
  }
};
</script>

<style>
.table-container {
	 height: calc(100vh - 450px);
}
 .table-container table {
	 display: flex;
	 flex-flow: column;
	 height: 100%;
	 width: 100%;
}
 .table-container table thead {
	 flex: 0 0 auto;
	 width: 100%;
}
 .table-container table tbody {
	 flex: 1 1 auto;
	 display: block;
	 width: 100%;
	 overflow-y: auto;
}
 .table-container table tbody tr {
	 width: 100%;
}
 .table-container table thead, .table-container table tbody tr {
	 display: table;
	 table-layout: fixed;
}
 .table-container table {
	 border-collapse: collapse;
}
 .table-container table td, .table-container table th {
	 padding: 0.4em;
}
 .table-container table th {
	 border: 1px solid black;
	 font-size: 0.7vw;
}
 .table-container table td {
	 border: 1px solid #e7e1e1;
	 font-size: 0.85em;
	/* necessary to set for proper "showing row x of y" calculations if infinate scoll */
	 white-space: nowrap;
	 text-align: center;
	 padding: 10px 5px;
	 white-space: nowrap;
	 text-overflow: ellipsis;
}
 .table-container table thead {
	 border: 2px solid #0F0FA3;
}
 .table-container th {
	 background-color: #0F0FA3;
	 color: #b5aba4;
	 cursor: pointer;
	 -webkit-user-select: none;
   -moz-user-select: none !important;
	 -ms-user-select: none;
	 user-select: none;
}
 .table-container table tbody td {
	 padding: 8px;
	 cursor: pointer;
}
 .table-container table tbody tr:hover {
	 background-color: rgba(168, 168, 239, .5);
}
 .table-container table thead td {
	 padding: 10px 5px;
}
 .table-container tr:nth-child(even) {
	 background-color: rgba(168, 168, 239, 1);
}

/* START Adjustments for width and scrollbar hidden */
 .table-container th.table-action, .table-container td.table-action {
	 width: 5.8vw;
}
 .table-container table thead {
	 width: calc(100% - 1px);
}
 .table-container table tbody::-webkit-scrollbar {
	 width: 1px;
}
 .table-container table tbody::-webkit-scrollbar {
	 width: 1px;
}
 .table-container table tbody::-webkit-scrollbar-thumb {
	 width: 1px;
}
/* END Adjustments for width and scrollbar */
</style>
