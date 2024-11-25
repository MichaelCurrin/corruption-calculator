<template>
  <div id="radiobutton">
    <input type="radio" id="one" value="20000" v-model="picked" />
    <label for="one">R 20 billion (2010)</label>
    <br />

    <input type="radio" id="two" value="25000" v-model="picked" />
    <label for="two">R 25 billion (2015)</label>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "Amount",
  data() {
    return {
      picked: "",
    };
  },
});
</script>
