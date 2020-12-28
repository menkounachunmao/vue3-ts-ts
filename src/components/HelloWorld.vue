<template>
  <div class="hello">
    <test-next-tickt></test-next-tickt>
  </div>
</template>

<script lang="ts">
import TestNextTickt from "./TestNextTick.vue";
import { Options, Vue } from "vue-class-component";

@Options({
  props: {
    msg: String,
  },
  components: { TestNextTickt },
})
export default class HelloWorld extends Vue {
  msg!: string;
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
