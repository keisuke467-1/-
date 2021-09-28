<template>
    <div class="masu" v-on:click="doAction">
        {{ masu }}
    </div>
</template>

<script>
export default {
    name: "masu",
    data() {
        return {
            masu: "",
        };
    },
    props: {
        count: Number,
    },
    methods: {
        doAction() {
            if(this.masu === "") {
                // 三項演算子…《真偽値》 ? 《trueの値》 : 《falseの値》
            this.masu = this.count % 2 === 0 ? "Don't worry" : "Be happy"
            this.$emit('count-event')
            } 
        },
    },
};
</script>

<style>
    .masu {
  width: 150px;
  height: 150px;
  border: 1px solid black;
  text-align: center;
  font-size: 80px;
  color: black;
  font-size: 20px;
}
</style>