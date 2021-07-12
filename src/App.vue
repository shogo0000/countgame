<template>
  <div>
    <AddButton @clickEvent="countUp" />
    <Display :count="count" />
  </div>
</template>

<script lang="ts">
import Display from "./components/Display.vue";
import AddButton from "./components/AddButton.vue";
import Component from "vue-class-component";
import { Vue, Watch } from "vue-property-decorator";

@Component({
  components: {
    AddButton,
    Display
  }
})
export default class App extends Vue {
  public count: number = 0;
  public countUp(): void {
    this.count++;
  }

  @Watch("count", { immediate: true })
  public finishCount(newValue: number): void {
    if (newValue > 10) {
      alert("finish");
      this.count = 0;
    }
  }
}
</script>