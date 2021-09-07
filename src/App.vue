<template>
<el-button> 我是 ElButton </el-button>
<ul>
  <li
    v-for="(item, index) in listData"
    :key="index"
  >
  {{item.problemID}}.{{item.problemContent}}
  <br>A.{{item.problemOption[0]}}
  <br>B.{{item.problemOption[1]}}
  <br>C.{{item.problemOption[2]}}
  <br>D.{{item.problemOption[3]}}
  </li>
</ul>

</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue'

interface Problem {
  problemID: number,
  problemType: number,
  problemContent: string,
  problemOption: string[]
}

export default defineComponent({
  setup () {
    const listData: Problem[] = reactive([
      {
        problemID: 1,
        problemType: 1,
        problemContent: '在内存储器中每个存储单元都被赋予一个唯一的序号，称为',
        problemOption: ["地址", "序号", "下标", "编号"]
      }
    ])
    return {
      listData
    }
  }
})
</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
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
