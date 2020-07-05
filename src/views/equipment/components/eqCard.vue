<template>
  <div class="card">
    <div class="iconLeft">
      <svg-icon :icon-class="eqInfo.icon" />
    </div>
    <div class="info">
      <div class="title">{{eqInfo.title}}</div>
      <div class="subTitle">{{eqInfo.en}}</div>
      <div class="desc">{{eqInfo.desc}}</div>
      <div class="budge">{{number+1}}</div>
      <div class="option">
        <div class="success">编辑</div>
        <div class="cancel">删除</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    eqInfo: {
      type: Object,
      default: () => ({})
    },
    number: {
      type: Number,
      default: 0
    }
  }
};
</script>


<style lang="scss" scoped>
.card {
  width: 33%;
  border: 1px solid #ddd;
  height: 130px;
  float: left;
  .iconLeft {
    font-size: 55px;
    text-align: center;
    float: left;
    vertical-align: middle;
    display: table-cell;
    color: #bbb;
    margin-left: 10px;
    width: 55px;
    margin-top: 16px;
  }
  .info {
    float: left;
    height: 130px;
    width: calc(100% - 80px);
    position: relative;
    padding-top: 20px;
    padding-left: 10px;
    .title {
      font-size: 16px;
    }
    .subTitle {
      color: #bbb;
      font-size: 14px;
    }
    .desc {
      color: #bbb;
      font-size: 12px;
      margin-top: 40px;
    }
  }
  .budge {
    width: 14px;
    height: 14px;
    position: absolute;
    background: #25a685;
    top: 20px;
    color: white;
    font-size: 14px;
    line-height: 14px;
    right: 0;
    text-align: center;
  }
  .option {
    font-size: 12px;
    width: 64px;
    text-align: center;
    position: absolute;
    bottom: 11px;
    right: 0;
    .success {
      border-radius: 2px;
      margin-bottom: 6px;
      padding: 2px;
      background: #67c23a66;
      box-shadow: 0 2px 4px rgba(103, 194, 58, 0.12), 0 0 6px rgba(103, 194, 58, 0.04);
      cursor: pointer;
      &:hover {
        box-shadow: 0 2px 4px rgba(103, 194, 58, 0.3), 0 0 6px rgba(103, 194, 58, 0.3);
      }
    }
    .cancel {
      border-radius: 2px;
      padding: 2px;
      cursor: pointer;
      background: #f56c6c66;
      &:hover {
        box-shadow: 0 2px 4px rgba(245, 108, 108, 0.3), 0 0 6px rgba(245, 108, 108, 0.3);
      }
      box-shadow: 0 2px 4px rgba(245, 108, 108, 0.12), 0 0 6px rgba(245, 108, 108, 0.04);
    }
  }
}
</style>