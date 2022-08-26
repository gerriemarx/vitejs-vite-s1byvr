<script>
export default {
  props: ['spinResultHistory']
}
</script>

<template>
  <table>
    <th>
      <td>#</td>
      <td>Result</td>
    </th>
    <tr v-for="(result, i) of spinResultHistory">
      <td>{{ i + 1 }}</td>
      <td>{{ result }}</td>
    </tr>
  </table>
</template>

<style scoped>
table, th, tr {
  display: flex;
}
table {
  flex-direction: column;
  border: 1px solid black;
}
th, tr {
  flex-direction: row;
  border: 1px solid black;
}
td {
  width: 50%;
  text-align: center;
}
td:first-of-type {
  border-right: 2px solid black;
}
</style>