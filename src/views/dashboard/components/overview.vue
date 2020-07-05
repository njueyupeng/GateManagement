<template>
  <div>
    <el-row :gutter="20">
      <el-col :xs="12" :sm="12" :lg="6" v-for="(item,index) in messageList" :key="index">
        <single-card :message="item" />
      </el-col>
    </el-row>
  </div>
</template>

<script>
import singleCard from "./card";
export default {
  components: { singleCard },
  data() {
    return {
      messageList: [
        {
          title: "楼宇总数",
          bubble: "Building",
          color: "#5AB1EF",
          info: [
            {
              num: 11,
              text: "Total Building"
            }
          ]
        },
        {
          title: "房间总数",
          bubble: "Room",
          color: "#2EC5C7",
          info: [
            {
              num: 800,
              text: "Total Room"
            }
          ]
        },
        {
          title: "人员总数",
          bubble: "People",
          color: "#AE9BD4",
          info: [
            {
              num: 1800,
              text: "Total People"
            }
          ]
        },
        {
          title: "开启记录",
          bubble: "Open log",
          color: "#ffb980",
          info: [
            {
              num: 36,
              text: "Total Log"
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