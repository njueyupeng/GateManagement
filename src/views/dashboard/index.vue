<template>
  <div>
    <overview-board />
    <campus-board :campus-list="campusList" />
    <building-board :building-list="buildingList" />
    <room-list />
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import overviewBoard from "./components/overview.vue";
import campusBoard from "./components/campusBoard.vue";
import buildingBoard from "./components/buildingBoard.vue";
import roomList from "./components/roomList.vue";

export default {
  name: "Dashboard",
  components: { overviewBoard, campusBoard, buildingBoard ,roomList},
  data() {
    return {
      campusList: [
        {
          title: "全部",
          en: "ALL",
          selected: false
        },
        {
          title: "东校区",
          en: "CAMPUS",
          selected: false
        },
        {
          title: "西校区",
          en: "CAMPUS",
          selected: false
        },
        {
          title: "南校区",
          en: "CAMPUS",
          selected: false
        },
        {
          title: "北校区",
          en: "CAMPUS",
          selected: false
        },
        {
          title: "莲花街校区",
          en: "CAMPUS",
          selected: false
        },
        {
          title: "龙子湖校区",
          en: "CAMPUS",
          selected: false
        }
      ],
      buildingList: [
        {
          title: "全部",
          en: "ALL",
          selected: false
        },
        {
          title: "体育馆",
          en: "CAMPUS",
          selected: false
        },
        {
          title: "教学楼",
          en: "CAMPUS",
          selected: false
        },
        {
          title: "实验楼",
          en: "CAMPUS",
          selected: false
        },
        {
          title: "宿舍楼",
          en: "CAMPUS",
          selected: false
        },
        {
          title: "图书馆",
          en: "CAMPUS",
          selected: false
        },
        {
          title: "艺术设计楼",
          en: "CAMPUS",
          selected: false
        },
        {
          title: "行政楼",
          en: "CAMPUS",
          selected: false
        },
        {
          title: "游泳馆",
          en: "CAMPUS",
          selected: false
        },
        {
          title: "办公楼",
          en: "CAMPUS",
          selected: false
        },
        {
          title: "雅食居",
          en: "CAMPUS",
          selected: false
        }
      ]
    };
  },
  computed: {}
};
</script>

<style lang="scss" scoped>
</style>
