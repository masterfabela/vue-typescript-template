<template>
  <div class="content">
    <p>{{ textToDisplay }}</p>
    <p>{{ textoComputed }}</p>
    <p>{{ property }}</p>
    <p>{{ getProperty() }}</p>
    <p>{{ storeValue }}</p>
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import store from "@/store";

export default Vue.extend({
  name: "OptionsApiComponent",
  data() {
    return {
      property: "heyyyyy",
    };
  },
  props: {
    textToDisplay: String,
  },
  methods: {
    getProperty() {
      return this.property;
    },
  },
  computed: {
    textoComputed(): string {
      return this.textToDisplay;
    },
    storeValue() {
      return store.state.dataVuexExample;
    },
  },
});
</script>

<style scoped lang="scss">
.content {
  height: 300px;
  background-color: aqua;
  p {
    background-color: red;
    color: #000;
  }
}
</style>
