<template>
<el-container>
  <el-main id="problem-main">
    <ProblemCard v-for="(item, index) in listData" :key="index" :problem="item">
    </ProblemCard>
  </el-main>
    <el-aside id="right-column">
    <AnswerSheet></AnswerSheet>
    </el-aside>
</el-container>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue'
import ProblemCard from '../components/ProblemCard.vue';
import AnswerSheet from '../components/AnswerSheet.vue';

interface Problem {
  problemID: number,
  problemType: number,
  problemContent: string,
  problemOption: string[]
}

export default defineComponent({
  name: "MainPage",
  components: {
    ProblemCard,
    AnswerSheet
  },
  setup () {
    const listData: Problem[] = reactive([
      {
        problemID: 1,
        problemType: 1,
        problemContent: '在内存储器中每个存储单元都被赋予一个唯一的序号，称为',
        problemOption: ["A.地址", "B.序号", "C.下标", "D.编号"]
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

<style lang="less" scoped>
  .el-aside {
    // background-color: #d3dce6;
    color: var(--el-text-color-primary);
    // text-align: center;
    // line-height: 200px;
  }

  .el-main {
    // background-color: #e9eef3;
    color: var(--el-text-color-primary);
    padding-top: 0px;
    // text-align: center;
    // line-height: 160px;
  }
.flex-container {
    #problem-main {
      flex: auto;
      margin-right: 18px;
      width: 70%;
    }
    #right-column {
      flex: auto;
      width: 30%;
    }
}
</style>
