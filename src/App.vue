<template>
  <h1>Corruption Calculator</h1>

  <h2>Material irregularity</h2>
  <Amount v-model="picked" />

  <h2>What that money could buy</h2>
  <Expenses v-model="checkedExpenses" />

  <Results :picked="picked" :checkedExpenses="checkedExpenses" :costing="costing" />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Amount from "./components/Amount.vue";
import Expenses from "./components/Expenses.vue";
import Results from "./components/Results.vue";

export default defineComponent({
  name: "App",
  components: {
    Amount,
    Expenses,
    Results,
  },
  data() {
    return {
      picked: 20000,
      checkedExpenses: [],
      costing: {
        defribulators: {
          name: "Defribulators",
          cost: 70000,
        },
        "hospital-beds": {
          name: "Hospital beds",
          cost: 24000,
        },
        "x-ray-machines": {
          name: "X-ray machines",
          cost: 120000,
        },
      },
    };
  },
});
</script>


<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
