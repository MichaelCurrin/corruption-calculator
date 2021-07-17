<template>
  <div id="multiple-checkboxes">
    <input
      type="checkbox"
      id="hospital-beds"
      value="hospital-beds"
      v-model="checkedExpenses"
      v-on:input="$emit('input', $event.target.value)"
    />
    <label for="hospital-beds">Hospital beds</label>

    <input
      type="checkbox"
      id="x-ray-machines"
      value="x-ray-machines"
      v-model="checkedExpenses"
      v-on:change="$emit('change', $event.target.checked)"
    />
    <label for="x-ray-machines">X-ray machines</label>

    <input
      type="checkbox"
      id="defribulators"
      value="defribulators"
      v-model="checkedExpenses"
      v-on:change="$emit('change', $event.target.checked)"
    />
    <label for="defribulators">Defribulators</label>

    <p>
      {{ checkedExpenses }}
    </p>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Expenses",
  data() {
    return {
      checkedExpenses: [],
    };
  },
});
</script>
