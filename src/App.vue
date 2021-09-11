<template>
  <!-- <div id="nav">
    <router-link to="/mainpage">About</router-link>
  </div> -->
<router-view />
<!-- <el-container>
  <el-main><ProblemCard v-for="(item, index) in listData" :key="index" :problem="item"></ProblemCard></el-main>
<el-aside width="300px">
  side
</el-aside>
</el-container> -->

</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue'
import ProblemCard from './components/ProblemCard.vue';

interface Problem {
  problemID: number,
  problemType: number,
  problemContent: string,
  problemOption: string[]
}

export default defineComponent({
  name: "App",
  components: {
    // ProblemCard
  },
  setup () {
    const listData: Problem[] = reactive([
      {
        problemID: 1,
        problemType: 1,
        problemContent: '在内存储器中每个存储单元都被赋予一个唯一的序号，称为',
        problemOption: ["A.地址dddddddddddddddddddd\ndddddddddddddddddaaaaaaaaaa\naaqqqqqqcddddddddddddddddddd\nddddddddddddddddddd\ndddddddddddddddddddd\ndddddddddddd", "B.序号", "C.下标", "D.编号"]
      },
      {
        problemID: 2,
        problemType: 2,
        problemContent: '111111在内存储器中每个存储单元都被赋予一个唯一的序号，称为',
        problemOption: ["A.地址", "B.序号", "C.下标", "D.编号"]
      },
      {
        problemID: 2,
        problemType: 2,
        problemContent: '111111\t在内存储器中每个存储单元都被赋予\n一个唯一的序号，称为,冒泡排序算法的伪代码如下：\n输入：数组L, n ≥ k。输出：按非递减顺序排序的 L。\n\n算法 BubbleSort：',
        problemOption: ["A.地址", "B.序号"]
      },
      {
        problemID: 2,
        problemType: 2,
        problemContent: '111111在内存储器中每个存储单元都被赋予一个唯一的序号，称为',
        problemOption: ["A.地址", "B.序号", "C.下标", "D.编号", "E.编号"]
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
