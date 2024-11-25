<template>
  <div>
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
          <li v-for="item in checkedExpenses" :key="item">
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
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Results",
  props: {
    picked: {
      type: Number,
      required: true,
    },
    checkedExpenses: {
      type: Array as () => string[],
      required: true,
    },
    costing: {
      type: Object as () => Record<string, { name: string; cost: number }>,
      required: true,
    },
  },
});
</script>

<style scoped>
div {
  margin: 0 auto;
  max-width: 800px;
  padding: 1rem;
}

ul {
  list-style-position: inside;
  padding-left: 1rem;
  margin-top: 1rem;
  margin-bottom: 1rem;
}

li {
  line-height: 1.5;
}
</style>
