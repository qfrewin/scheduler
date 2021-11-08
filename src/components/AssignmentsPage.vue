<template>

  <div>
    <div class="wrapper">
      <div class="table-title">
        <h1>Assignments Page</h1>
      </div>
      <div class="table-assignments">
        <table>
          <tr>
            <th v-for="heads in table[0]">
              {{ heads.name }}
            </th>
          </tr>
          <tr v-for="(rows, i) in table.slice(1)">
            <td>{{ table[i + 1][0].name }}</td>
            <td v-for="(cols, j) in table[i + 1].slice(1)" >
              <InputCell
                :cellValue="table[i + 1][j + 1].name"
                :row="i + 1" :col="j + 1"
                :tableColors="tableColors"
                @valueChanged="table[i + 1][j + 1].name = $event"
                >
              </InputCell>
            </td>
          </tr>
        </table>
      </div>
    </div>

  </div>

</template>

<script>

import InputCell from './InputCell.vue';

export default {
  name: 'AssignmentsPage',

  components: {
    InputCell
  },

  props: {
    classes: Array,
    tableColors: Object,
    table: Array
  }
}

</script>

<style>

table {
  border-collapse: collapse;
}

td, th {
  border: solid 1px black;
  width: 100%;
  height: 100%;
  white-space: nowrap;
}

td {
  font-size: 14px;
}

tr {
  height: 100%;
}

tr:nth-child(odd) {
  background-color: #def4f4;
}

tr:first-child {
  background-color: #0abab4;
  color: white;
}

</style>
