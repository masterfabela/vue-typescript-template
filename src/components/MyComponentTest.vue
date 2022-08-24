<template>
  <div class="content">
    <p>{{ textToDisplay }}</p>
    <p>{{ textoComputed() }}</p>
    <p>{{ property }}</p>
    <p>{{ getProperty() }}</p>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from "vue-property-decorator";

@Component
export default class MyComponentTest extends Vue {
  @Prop({ default: "valor defecto" }) readonly textToDisplay: string;

  property = "heyyyyy";

  textoComputed() {
    return this.textToDisplay;
  }

  getProperty() {
    return this.property;
  }

  created() {
    console.log("Component created");
  }

  mounted() {
    console.log("Component Mounted");
    console.log(this.textToDisplay);
  }
}
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
