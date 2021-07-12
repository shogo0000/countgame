<template>
  <div>
    <button @click="clickEvent">push</button>
  </div>
</template>

<script lang="ts">
import Component from "vue-class-component";
import { Vue, Emit } from "vue-property-decorator";

@Component
export default class Addbutton extends Vue {
  @Emit("clickEvent")
  public clickEvent(): void {}
}
</script>
