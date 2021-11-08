<template>

<div>
  <AssignmentsPage :classes="classes" :tableColors="tableColors" :table="table"/>
</div>

</template>

<script>
  import AssignmentsPage from "../components/AssignmentsPage.vue";

  export default {
    name: 'Assignments',

    data() {
      return {
        title: "Assignments"
      }
    }

    components: {
      AssignmentsPage
    },

    computed: {
      classes() {
        return this.$root.$data.classes;
      },
      tableColors() {
        return this.$root.$data.tableColors;
      },
      table() {
        return this.$root.$data.tables.assignmentTable;
      }
    }
  }

</script>

<style>



</style>
