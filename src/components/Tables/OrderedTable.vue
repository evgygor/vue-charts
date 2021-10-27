<template>
  <div>
    <md-table v-model="groups.mdData" :table-header-color="tableHeaderColor">
      <md-table-row slot="md-table-row" slot-scope="{ item }">
        <md-table-cell md-label="Name">{{ item.name }}</md-table-cell>
        <md-table-cell md-label="Total Budget">{{ item.total_budget }}</md-table-cell>
        <md-table-cell md-label="Total Cost">{{ item.total_envs }}</md-table-cell>
        <md-table-cell md-label="Used Budget">{{ item.used_budget }}</md-table-cell>
      </md-table-row>
    </md-table>
  </div>
</template>

<script>
export default {
  name: "ordered-table",
  props: {
    tableHeaderColor: {
      type: String,
      default: "",
    },
  },

  data: () => ({
    groups: {
      mdData: []
    },
  }),
  async created () {
    const response = await fetch("http://localhost:3000/groups");
    const data = await response.json();
    // console.log(data)
      this.groups = {
        mdData: data
      }
  },
};
</script>
