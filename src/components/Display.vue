<template>
  <div>
    <p>click button {{ count }}</p>
    <p>スコア {{ doubledCount }}</p>
  </div>
</template>

<script lang="ts">
import Component from "vue-class-component";
import { Prop, Vue } from "vue-property-decorator";

@Component
export default class Display extends Vue {
  @Prop()
  public count!: number;

  public get doubledCount(): number {
    return this.count * 2;
  }
}
</script>