<template>
  <div class="person-container">
    <div class="container">
      <header>设备列表</header>
      <div class="divide"></div>
      <div class="option">
          <el-button type="success"  size="mini">添加设备</el-button>
      </div>
      <div class="cardBoard">
        <eq-card v-for="(eq,index) in eqList" :key="index" :number="index" :eq-info="eq" />
      </div>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import eqCard from "./components/eqCard.vue";

export default {
  name: "Person",
  components: { eqCard },
  computed: {
    ...mapGetters(["name"])
  },
  data() {
    return {
      eqList: [
        { icon: "suo", title: "锁", en: "THE LOCK", desc: "智能控制锁体" },
        {
          icon: "kongtiao",
          title: "空调",
          en: "CONDITION",
          desc: "智能控制锁体"
        },
        { icon: "deng", title: "灯", en: "THE LAMP", desc: "智能控制锁体" },
        {
          icon: "baojing",
          title: "烟雾报警器",
          en: "SMOKE ALARM",
          desc: "便捷操作沐浴阳光"
        },
        {
          icon: "kaiguan",
          title: "电控开关",
          en: "SWITCH KNOB",
          desc: "智能控制锁体"
        },
        {
          icon: "caiji",
          title: "采集器",
          en: "COLLERCTOR",
          desc: "智能控制锁体"
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.container {
  background: #fff;
  border-radius: 4px;
  min-height: 500px;
  header {
    font-weight: 400;
    padding: 8px;
  }
  .cardBoard {
    padding: 16px;
  }
  .divide {
    width: 100%;
    border-bottom: 1px solid #ddd;
  }
  .option{
    padding: 20px;
  }
}
</style>
