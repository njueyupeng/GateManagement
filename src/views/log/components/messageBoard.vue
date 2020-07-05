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
          title: "总记录数",
          info: [
            {
              num: 102400,
              text: "Total log"
            }
          ]
        },
        {
          title: "今日记录",
          info: [
            {
              num: 800,
              text: "Today log"
            }
          ]
        },
        {
          title: "人员总数",
          info: [
            {
              num: 1800,
              text: "Total people"
            }
          ]
        },
        {
          title: "覆盖人数",
          info: [
            {
              num: 36,
              text: "Number"
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