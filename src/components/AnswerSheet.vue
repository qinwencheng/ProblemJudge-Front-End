<template>
<el-card >

  <template #header>
    <div class="card-header">
      <span>倒计时</span>
      <span>共60题</span>
    </div>
  </template>

  <ul class="ul">
    <li class="li" v-for="i in 1177" :key="i" >
      <el-button class="button">{{i}}</el-button>
    </li>
  </ul>

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
.button {
  width: 20%;
  display: flex;
  justify-content: center;/* button 内文字居中 */
  /* align-items: center; */
  margin:0 auto; /* button 相对li居中 */
  /* text-align:center; */
}
.ul {
  /* text-align:center; */
  padding: 0;
  margin-top: 0px;
  display: flex;
  flex-wrap: wrap;
  width: 100%;
  list-style-type: none;
  /* align-items: center; */
  /* text-align: center; */
  /* flex-direction: row;
  justify-content: center; */
}
.li {
  /* text-align:center; */
  /* align-items: center; */
  /* text-align: center; */
  /* justify-content: center; */
  width: 20%;
  padding-top: 10px;
  /* text-align: center; */
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

  .answer-sheet-card {
    padding: 0px;
  }
</style>
