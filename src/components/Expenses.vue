<template>
  <div id="multiple-checkboxes">
    <input type="checkbox" id="hospital-beds" value="hospital-beds"
      :checked="modelValue.includes('hospital-beds')"
      @change="updateChecked('hospital-beds', $event.target.checked)" />
    <label for="hospital-beds">Hospital beds</label>

    <input type="checkbox" id="x-ray-machines" value="x-ray-machines"
      :checked="modelValue.includes('x-ray-machines')"
      @change="updateChecked('x-ray-machines', $event.target.checked)" />
    <label for="x-ray-machines">X-ray machines</label>

    <input type="checkbox" id="defribulators" value="defribulators"
      :checked="modelValue.includes('defribulators')"
      @change="updateChecked('defribulators', $event.target.checked)" />
    <label for="defribulators">Defribulators</label>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Expenses",
  props: {
    modelValue: {
      type: Array as () => string[],
      required: true,
    },
  },
  methods: {
    updateChecked(item: string, isChecked: boolean) {
      const updated = isChecked
        ? [...this.modelValue, item]
        : this.modelValue.filter((i) => i !== item);

      this.$emit("update:modelValue", updated);
    },
  },
});
</script>
