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
          <div class="subTitle">
            <i class="el-icon-success" />
            添加新校区
          </div>
        </div>
      </div>
      <div v-for="(item,index) in campusList" :key="index">
        <div class="card" :class="{color1:index%3===0,color2:index%3===1,color3:index%3===2,}">
          <div class="title">{{item.title}}</div>
          <div class="enTitle">{{item.en}}</div>
          <div class="subTitle">
            <i class="el-icon-success" />
            {{item.title}}
          </div>
        </div>
      </div>
      <div style="clear:both"></div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    campusList: {
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
      return (this.campusList.length + 1) * 134;
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
  padding-bottom: 40px;
}
.addCard {
  cursor: pointer;
  width: 120px;
  position: relative;
  height: 60px;
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
    position: absolute;
    color: rgb(187, 187, 187);
    top: 40px;
    font-size: 12px;
    width: 120px;
    text-align: center;
  }
}
.card {
  position: relative;
  width: 120px;
  height: 60px;
  padding: 10px 20px;
  float: left;
  margin-right: 14px;

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
  .title {
    color: #fff;
    line-height: 18px;
    margin-bottom: 2px;
  }
  .enTitle {
    color: rgba(255, 255, 255, 0.5);
    font-weight: 500;
  }
}
.color1 {
  background: #0078d7b8;
}

.color2 {
  background: #4eb9b7b8;
}

.color3 {
  background: #ec868fb8;
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
    top: 22px;
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
    top: 22px;
    right: 0;
    width: 40px;
    height: 20px;
  }
}
</style>