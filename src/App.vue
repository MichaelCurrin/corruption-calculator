<template>
  <h1>Corruption Calculator</h1>

  <h2>Material irregularity</h2>

  <Amount v-model="picked" />

  <h2>What that money could buy</h2>

  <div id="multiple-checkboxes">
    <input type="checkbox" id="hospital-beds" value="hospital-beds" v-model="checkedExpenses" />
    <label for="hospital-beds">Hospital beds</label>

    <input type="checkbox" id="x-ray-machines" value="x-ray-machines" v-model="checkedExpenses" />
    <label for="x-ray-machines">X-ray machines</label>

    <input type="checkbox" id="defribulators" value="defribulators" v-model="checkedExpenses" />
    <label for="defribulators">Defribulators</label>
  </div>

  <h2>Results</h2>
  <p>
    Calculation results infographic which you are encouraged to share on social
    media.
  </p>

  <div>
    <h3>COST OF CORRUPTION</h3>

    <p>
      <b>R {{ picked.toLocaleString() }} billion</b>
    </p>

    <div v-if="checkedExpenses.length">
      <p>That money could have paid for...</p>

      <p>
        {{ checkedExpenses.length }} categories allocated R
        {{ ((10 ** 6 * picked) / checkedExpenses.length).toLocaleString() }} each
      </p>

      <ul>
        <li v-for="item in checkedExpenses" :key="item.id">
          {{
            (
              (10 ** 6 * picked) /
              checkedExpenses.length /
              costing[item].cost
            ).toLocaleString()
          }} {{ costing[item].name }} at R {{ costing[item].cost.toLocaleString() }} each
        </li>
      </ul>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import Amount from "./components/Amount.vue";

export default defineComponent({
  name: "App",
  components: {
    Amount,
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
