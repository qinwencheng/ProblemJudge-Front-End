<template>
<el-card class="box-card">

  <template #header>
    <div class="card-header">
      <span class="isp">{{num}}.{{problem.problemContent}}</span>
    </div>
  </template>
  <!-- <div>
    <span v-for="(option, index) in problem.problemOption" :key="index">{{option}}<br></span>
  </div> -->
    <!-- <el-radio-group v-model="radio">
      <div class="ww" v-for="(option, index) in problem.problemOption" :key="index" >
      <el-radio :label="index" >{{option}}</el-radio>
      </div>
    </el-radio-group> -->

<el-radio-group v-model="radio">
<el-row>
  <el-col :span="24" v-for="(option, index) in problem.problemOption" :key="index">
    <el-radio :label="index"><div class="text-wrapper">{{option}}</div></el-radio>
  </el-col>
</el-row>
</el-radio-group>
</el-card>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue'

export default defineComponent({
  name: "ProblemCard",
  props: {
    problem: Object,
    num: Number
    // problemID: Number,
    // problemType: Number,
    // problemContent: String,
    // problemOption: Array
  },
  components: {
  },
  setup () {
    const c = () => {
      console.log(arguments)
    }
    return {
      radio: ref(-1),
      c
    }
  }
})
</script>

<style scoped>
.text-wrapper {
  word-break: break-all;
  word-wrap: break-word;
  white-space: pre-wrap;
}
.isp {
  white-space: pre-wrap;
}
.w {
  width: 100%;
}
.ww {
  display: inline-block;
  width: 50%;
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
