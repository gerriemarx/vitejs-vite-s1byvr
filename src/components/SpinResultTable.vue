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
