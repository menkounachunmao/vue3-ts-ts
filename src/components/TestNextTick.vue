<template>
  <div>
    <div ref="word">
      {{ wordTest }}
    </div>
    <button @click="changeData">change</button>
  </div>
</template>

<script lang="ts">
import { Options, Vue } from "vue-class-component";

@Options({})
export default class TestNextTickt extends Vue {
  wordTest = "wordTest";
  // 不是插入到任务队列最尾部。
  // nextTick还是之前值(后面值改变的任务插入在了nexTick回调之后)，
  // vue的dom更新也是异步
  changeData() {
    let wordTemp = this.$refs.word as Element;
    console.log(wordTemp.innerHTML);
    // this.wordTest = "changedStart";
    this.$nextTick(() => console.log(wordTemp.innerHTML));
    setTimeout(() => {
      console.log(wordTemp.innerHTML);
    }, 100);
    this.wordTest = "changedEnd";
  }
  
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped></style>
