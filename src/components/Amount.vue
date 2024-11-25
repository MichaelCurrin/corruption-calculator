<template>
  <div>
    <div id="radiobutton">
      <input type="radio" id="one" value="20000" :checked="modelValue === 20000"
        @change="$emit('update:modelValue', 20000)" />
      <label for="one">R 20 billion (2010)</label>
      <br />

      <input type="radio" id="two" value="25000" :checked="modelValue === 25000"
        @change="$emit('update:modelValue', 25000)" />
      <label for="two">R 25 billion (2015)</label>
    </div>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Amount",
  props: {
    modelValue: {
      type: Number,
      required: true,
    },
  },
});
</script>
