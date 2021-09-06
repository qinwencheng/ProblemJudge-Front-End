<template>
  <div>count:{{state.count}}</div>
  <button @click="inc">{{state.count}}</button>
</template>

<script setup lang="ts">
import { reactive, computed } from "vue";
type k = {
  count: number;
  double: number;
}
const state: k = reactive({
  count: 0,
  double: computed(() => state.count * 2)
})
function inc () {
  state.count++;
}
</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

#nav {
  padding: 30px;

  a {
    font-weight: bold;
    color: #2c3e50;

    &.router-link-exact-active {
      color: #42b983;
    }
  }
}
</style>
