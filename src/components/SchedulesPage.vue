schedules<template>

  <div>
    <div class="wrapper">
      <div class="table-schedules">
        <table>
          <thead>
            <tr>
              <th v-for="heads in table[0]">
                {{ heads.name }}
              </th>
            </tr>
          </thead>
          <tbody>
            <tr v-for="(rows, i) in table.slice(1)">
              <td class="freeze-col">{{ table[i + 1][0].name }}</td>
              <td v-for="(cols, j) in table[i + 1].slice(1)" >
                <ScheduleCell
                  :cellValue="table[i + 1][j + 1].name"
                  :row="i + 1" :col="j + 1"
                  :tableColors="tableColors"
                  @valueChanged="table[i + 1][j + 1].name = $event"
                  >
                </ScheduleCell>
              </td>
            </tr>
          </tbody>
        </table>
      </div>
    </div>

  </div>

</template>

<script>

import ScheduleCell from './ScheduleCell.vue';

export default {
  name: 'schedulesPage',

  components: {
    ScheduleCell
  },

  props: {
    classes: Array,
    tableColors: Object,
    table: Array
  },

  methods: {
    makeId(row, col) {
      return "schedules row: " + i + " col: " + j;
    }
  }
}

</script>

<style>

.table-schedules {
  max-height: 80vh;
  overflow: auto;
  max-width: 100vw;
}

table {
  margin-left: 20px;
  margin-bottom: 20px;
  border-collapse: separate;
  border-spacing: 0;
  position: relative;
  border-right: 2px solid black;
  border-bottom: 2px solid black;
}

td, th {
  width: 100%;
  height: 100%;
  white-space: nowrap;
}

.table-schedules td:nth-child(odd) input {
  width: 25px;
  -webkit-transform: rotate(90deg);
  -moz-transform: rotate(90deg);
}

td {
  border-right: solid 1px black;
  border-bottom: solid 1px black;
  font-size: 14px;
  overflow: hidden;
}

td:first-child {
  padding-right: 2px;
  padding-left: 2px;
}

tr:nth-child(even),
tr:nth-child(even) .freeze-col {
  background-color: #def4f4;
}
tr:nth-child(odd),
tr:nth-child(odd) .freeze-col {
  background-color: white;
}

th {
  background-color: #0abab4;
  color: white;
  padding: 2px;
  position: sticky;
  top: 0;
  z-index: 2;
  border-bottom: 2px solid black;
  border-right: 1px solid black;
  border-top: 2px solid black;
}
th:first-child {
  border-right: 2px solid black;
  z-index: 3;
  left: 0;
  border-left: 3px solid black;
}

.freeze-col {
  position: sticky;
  left: 0;
  border-right: 2px solid black;
  border-left: 3px solid black;
}


</style>
