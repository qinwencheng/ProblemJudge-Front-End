
<template>
<el-row>
  <el-col :span="12"><div class="grid-content bg-purple"></div></el-col>
  <el-col :span="12"><div class="grid-content bg-purple-light"></div></el-col>
</el-row>
<el-card class="box-card">
  <template #header>
    <div class="card-header">
      <span>{{problem.problemID}}.{{problem.problemContent}}</span>
    </div>
  </template>
  <!-- <div>
    <span v-for="(option, index) in problem.problemOption" :key="index">{{option}}<br></span>
  </div> -->
  <el-row>
  <div class="w">
    <el-radio-group v-model="radio">
      <el-col :span="12">
      <div v-for="(option, index) in problem.problemOption" :key="index" >
      <el-radio :label="index" >{{option}}</el-radio>
      </div>
      </el-col>
    </el-radio-group>
  </div>
  </el-row>
  <!-- <div v-for="o in 4" :key="o" class="text item">{{'列表内容 ' + o }}</div> -->
</el-card>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: "ProblemCard",
  props: {
    problem: Object
    // problemID: Number,
    // problemType: Number,
    // problemContent: String,
    // problemOption: Array
  },
  components: {
    // ElButton,
    // ElCard
  },
  setup () {
    return {
      radio: ref(-1)
    }
  }
})
</script>

<style>
  .w {
    width: 100%;
  }
  .el-row {
    margin-bottom: 20px;
    &:last-child {
      margin-bottom: 0;
    }
  }
  .el-col {
    border-radius: 4px;
  }
  .bg-purple-dark {
    background: #99a9bf;
  }
  .bg-purple {
    background: #d3dce6;
  }
  .bg-purple-light {
    background: #e5e9f2;
  }
  .grid-content {
    border-radius: 4px;
    min-height: 36px;
  }
  .row-bg {
    padding: 10px 0;
    background-color: #f9fafc;
  }
.card-header {
    display: flex;
    justify-content: space-between;
    align-items: center;
  }

  .text {
    font-size: 14px;
  }

  .item {
    margin-bottom: 18px;
  }

  .box-card {
    width: 100%;
  }
</style>
