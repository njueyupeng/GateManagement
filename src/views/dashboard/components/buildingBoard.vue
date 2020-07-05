<template>
  <div class="board">
    <div class="left" @click="toLeft">
      <i class="el-icon-arrow-left" />
    </div>
    <div class="right" @click="toRight">
      <i class="el-icon-arrow-right" />
    </div>
    <div class="scrollBar" :style="{width:scrollBarWidth+'px',left:scrollBarLeft+'px'}">
      <div>
        <div class="addCard">
          <i class="el-icon-circle-plus-outline" />
          <div style="font-size:12px" class="subTitle">添加楼</div>
        </div>
      </div>
      <div v-for="(item,index) in buildingList" :key="index">
        <div
          class="card"
          :class="{color1:index%4===0,color2:index%4===1,color3:index%4===2,color4:index%4===3}"
        >
          <svg-icon icon-class="building" />
          <div class="title">{{item.title}}</div>
          <span class="wave" :class="{bgcolor1:index%4===0,bgcolor2:index%4===1,bgcolor3:index%4===2,bgcolor4:index%4===3}"></span>
          <span class="wave" :class="{bgcolor1:index%4===0,bgcolor2:index%4===1,bgcolor3:index%4===2,bgcolor4:index%4===3}"></span>
          <span class="wave" :class="{bgcolor1:index%4===0,bgcolor2:index%4===1,bgcolor3:index%4===2,bgcolor4:index%4===3}"></span>
        </div>
      </div>
      <div style="clear:both"></div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    buildingList: {
      type: Array,
      default: () => []
    }
  },
  data() {
    return {
      scrollBarLeft: 0
    };
  },
  computed: {
    scrollBarWidth() {
      return (this.buildingList.length + 1) * 98;
    }
  },
  methods: {
    toLeft() {
      if (this.scrollBarLeft < 0) {
        this.scrollBarLeft += 500;
      }
    },
    toRight() {
      if (this.scrollBarLeft * -1 + 500 < this.scrollBarWidth) {
        this.scrollBarLeft -= 500;
      }
    }
  }
};
</script>

<style  lang="scss" scoped>
.scrollBar {
  position: relative;
  transition-timing-function: ease-in-out;
  transition-duration: 0.5s;
  padding-bottom: 20px;
}
.addCard {
  cursor: pointer;
  background: white;
  text-align: center;
  width: 84px;
  box-shadow: 3px 1px 4px rgba(119, 117, 117, 0.3);
  position: relative;
  height: 106px;
  line-height: 60px;
  font-size: 20px;
  color: #bbb;
  border: 1px dotted #bbb;
  float: left;
  margin-right: 14px;
  display: table-cell;
  vertical-align: middle;
  text-align: center;
  .subTitle {
    position: relative;
    top: -35px;
  }
}
.card {
  text-align: center;
  background: white;
  position: relative;
  font-size: 32px;
  width: 84px;
  height: 106px;
  overflow: hidden;
  padding: 10px 10px;
  float: left;
  margin-right: 14px;
  box-shadow: 3px 1px 4px rgba(119, 117, 117, 0.3);
  border: 2px solid #bbbbbb4d;
  cursor: pointer;
  .subTitle {
    position: relative;
    color: rgb(187, 187, 187);
    top: 17px;
    font-size: 12px;
    width: 120px;
    text-align: center;
    left: -20px;
  }
  .wave {
    width: 50px;
    height: 50px;
    display: inherit;
    position: absolute;
    left: -15px;
    border-radius: 30px;
    bottom: -34px;
  }
  .wave:nth-child(2n) {
    left: 20px;
  }
  .wave:nth-child(3n) {
    left: 40px;
  }
  .title {
    line-height: 18px;
    font-size: 12px;
    margin-bottom: 2px;
  }
  .enTitle {
    color: rgba(255, 255, 255, 0.5);
    font-weight: 500;
  }
}
.color1 {
  color: #0078d7b8;
}

.color2 {
  color: #e6a23cb8;
}
.color3 {
  color: #4eb9b7b8;
}

.color4 {
  color: #ec868fb8;
}
.bgcolor1 {
  background: #0078d72b;
}

.bgcolor2 {
  background: #e6a23c2b;
}
.bgcolor3 {
  background: #4eb9b72b;
}

.bgcolor4 {
  background: #ec868f2b;
}
.board {
  overflow: hidden;
  position: relative;
  padding: 0 10px;
  .left {
    background: rgba(00, 00, 00, 0.3);
    color: white;
    line-height: 20px;
    text-align: center;
    position: absolute;
    cursor: pointer;
    top: 46px;
    left: 0;
    z-index: 1;
    width: 40px;
    height: 20px;
  }
  .right {
    z-index: 1;
    background: rgba(00, 00, 00, 0.3);
    color: white;
    line-height: 20px;
    text-align: center;
    position: absolute;
    cursor: pointer;
    top: 46px;
    right: 0;
    width: 40px;
    height: 20px;
  }
}
</style>