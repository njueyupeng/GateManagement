<template>
  <div class="person-card">
    <div class="header">
      <span class="title">{{message.title}}</span>
      <span class="badage">{{message.badage||'Today'}}</span>
    </div>
    <div class="container">
      <div v-for="(info,index) in message.info" :key="index" style="width:45%">
        <count-to :start-val="0" :end-val="info.num" :duration="1600" class="card-panel-num" />
        <div class="card-panel-text">{{info.text}}</div>
      </div>
    </div>
  </div>
</template>

<script>
import CountTo from "vue-count-to";
export default {
  name: "personCard",
  components: { CountTo },
  props: {
    message: {
      default: () => ({
        title: "",
        badage: "",
        info: []
      }),
      type: Object
    }
  }
};
</script>

<style lang="scss" scoped>
.person-card {
  min-height: 50px;
  font-size: 12px;
  border-radius: 4px;
  background-color: #fff;
  overflow: hidden;
  box-shadow: 4px 4px 40px rgba(0, 0, 0, 0.05);
  border-color: rgba(0, 0, 0, 0.05);
  &:hover {
    box-shadow: 4px 4px 40px rgba(0, 0, 0, 0.2);
  }
  margin-bottom: 16px;
  cursor: pointer;
  .header {
    padding: 8px;
    border-bottom: 1px solid #ddd;
    .title {
      font-weight: 300;
    }
    .badage {
      background: rgba(100, 217, 214, 0.7);
      padding: 2px;
      border-radius: 2px;
      float: right;
    }
  }
  .container {
    padding: 16px;
    min-height: 56px;
    display: flex;
    justify-content: start;
    .card-panel-text {
      line-height: 18px;
      color: rgba(0, 0, 0, 0.45);
      font-size: 14px;
      //   margin-bottom: 12px;
    }

    .card-panel-num {
      font-size: 20px;
    }
  }
}
</style>
