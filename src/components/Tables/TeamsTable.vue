<template>
  <div>
    <md-table v-model="teams" :table-header-color="tableHeaderColor">
      <md-table-row slot="md-table-row" slot-scope="{ item }">
        <md-table-cell md-label="ID">{{ item.id }}</md-table-cell>
        <md-table-cell md-label="Name">{{ item.name }}</md-table-cell>
        <md-table-cell md-label="Started Builds">{{ item.started_builds }}</md-table-cell>
      </md-table-row>
    </md-table>
  </div>
</template>

<script>
export default {
  name: "teams-table",
  props: {
    tableHeaderColor: {
      type: String,
      default: "",
    },
    selectedTeam:""
  },
  data() {
    return {
      teams: [],
    };
  },
  async created () {
     try {
        let response = await fetch(`http://localhost:3000/${this.selectedTeam}`);
        this.teams = await response.json();   
        console.log(this.teams)
      } catch (error) {
        console.log(error);
      }
  },
};
</script>
