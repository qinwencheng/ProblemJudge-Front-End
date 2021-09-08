<template>
<el-card class="box-card">
  <template #header>
    <div class="card-header">
      <span>倒计时</span>
      <span>共60题</span>
    </div>
  </template>
  <el-row>
    <el-col :lg="6" >
    <div>
      <el-button plain v-for="i in 3" :key="i">{{i}}</el-button>
    </div>
    </el-col>
  </el-row>
</el-card>
</template>

<script lang="ts">
import { defineComponent, reactive } from 'vue'
export default defineComponent({
  name: 'AnswerSheet',
  components: {
  }
})
</script>

<style scoped>
.el-row {
    margin-bottom: 20px;

  }
  .el-col {
    border-radius: 4px;
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
    /* width: 480px; */
  }
</style>
