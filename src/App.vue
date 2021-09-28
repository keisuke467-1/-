<template>
  <div class="board">
    <!-- ・v-forを使って、必要なマス目の数だけ作成する 
         ・v-bindの有無により、要素の削除と要素の上書きの差がある-->
        <masu 
        v-bind:count="count"
        v-for="n of 9"
        v-bind:key="n"
        v-on:count-event="doCountUp"
        />
        <p class="abc">Don't worry <br>Be happy</p>
    </div>
</template>

<script>
// masu.vueからmasuを読み込む
import masu from './components/masu.vue'

export default {
  name: 'App',
  data() {
    return {
      count: 0,
    };
  },
  components: {
    masu,
  },
  methods: {
    doCountUp() {
      this.count += 1;
    }
  }
}
</script>

<style>
.board {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  width: 450px;
}
.abc {
  font-size: 20px;
}
</style>
