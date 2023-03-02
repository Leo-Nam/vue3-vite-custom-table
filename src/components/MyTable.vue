<template>
  <table>
    <tr>
      <th v-for="(head, head_index) in tableData.header" :key="'head-' + head_index">
        {{ head }}
      </th>
    </tr>
    <tr v-for="(row, row_index) in tableData.rows" :key="'row-' + row_index">
      <td
        v-for="(data, data_index) in row"
        :key="'data-' + data_index"
        :colspan="data.colspan || 1"
      >
        {{ data.data }}
      </td>
    </tr>
  </table>
</template>

<script>
export default {
  props: ['tableData']
}
</script>

<style scoped>
table, th, td {
  border: 1px solid black;
  border-collapse: collapse;
  padding: 5px;
}
</style>