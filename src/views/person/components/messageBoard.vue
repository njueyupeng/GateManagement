<template>
  <div>
    <el-row :gutter="20">
      <el-col :xs="12" :sm="12" :lg="6" v-for="(item,index) in messageList" :key="index">
        <person-card :message="item" />
      </el-col>
    </el-row>
  </div>
</template>

<script>
import personCard from "./personCard";
export default {
  components: { personCard },
  data() {
    return {
      messageList: [
        {
          title: "今日日志",
          info: [
            {
              num: 102400,
              text: "Log today"
            }
          ]
        },
        {
          title: "今日活跃",
          info: [
            {
              num: 800,
              text: "active today"
            }
          ]
        },
        {
          title: "人员统计",
          info: [
            {
              num: 1800,
              text: "在校人数"
            },
            {
              num: 900,
              text: "其他人数"
            }
          ]
        },
        {
          title: "日志统计",
          info: [
            {
              num: 36,
              text: "日志数量"
            },
            {
              num: 12,
              text: "学生记录数"
            }
          ]
        }
      ]
    };
  }
};
</script>

<style>
</style>