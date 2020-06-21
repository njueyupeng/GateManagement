<template>
  <div class="person-list">
    <header>人员列表</header>
    <div class="divide"></div>
    <div class="filter">
      <div class="grade">
        <span
          v-for="(item,index) in gradeList"
          :key="index"
          :class="{active:selectEdGrade===item}"
          class="filterItems"
          @click="selectGrade(item)"
        >{{item}}</span>
      </div>
      <div class="divide-middle"></div>
      <div class="college">
        <span
          v-for="(item,index) in collegeList"
          :key="index"
          :class="{active:selectedCollege===item}"
          class="filterItems"
          @click="selectCollege(item)"
        >{{item}}</span>
      </div>
      <div class="divide"></div>
    </div>
    <div class="containter">
      <personal-card v-for="(item,index) in filterList" :person="item" :key="index" />
      <div v-if="filterList.length===0">空</div>
      <div style="clear:both"></div>
    </div>
  </div>
</template>

<script>
import personalCard from "./personalCard";

export default {
  components: { personalCard },
  data() {
    return {
      gradeList: ["全部", 2020, 2019, 2018, 2017, 2016],
      selectEdGrade: "全部",
      selectedCollege: "全部",
      collegeList: [
        "全部",
        "商学院",
        "医学院",
        "土木工程",
        "音乐学院",
        "水利学院",
        "计算机学院",
        "新闻传播学院"
      ],
      personList: [
        {
          name: "张天爱",
          grade: "2020",
          pinyin: "ZhangTianAi",
          college: "音乐学院"
        },
        {
          name: "张大宝",
          grade: "2020",
          pinyin: "ZhangTianAi",
          college: "商学院"
        },
        {
          name: "郭德纲",
          grade: "2019",
          pinyin: "ZhangTianAi",
          college: "计算机学院"
        },
        {
          name: "凌霄",
          grade: "2016",
          pinyin: "ZhangTianAi",
          college: "土木工程"
        },
        {
          name: "宁采臣",
          grade: "2019",
          pinyin: "ZhangTianAi",
          college: "商学院"
        },
        {
          name: "张三",
          grade: "2019",
          pinyin: "ZhangTianAi",
          college: "音乐学院"
        },
        {
          name: "李四",
          grade: "2017",
          pinyin: "ZhangTianAi",
          college: "音乐学院"
        },
        {
          name: "郭晶晶",
          grade: "2019",
          pinyin: "ZhangTianAi",
          college: "音乐学院"
        },
        {
          name: "赵本山",
          grade: "2018",
          pinyin: "ZhangTianAi",
          college: "音乐学院"
        },
        {
          name: "李晶晶",
          grade: "2019",
          pinyin: "ZhangTianAi",
          college: "音乐学院"
        },
        {
          name: "王菲",
          grade: "2020",
          pinyin: "ZhangTianAi",
          college: "计算机学院"
        },
        {
          name: "谢大脚",
          grade: "2019",
          pinyin: "ZhangTianAi",
          college: "音乐学院"
        },
        {
          name: "华晨宇",
          grade: "2016",
          pinyin: "ZhangTianAi",
          college: "商学院"
        },
        {
          name: "杨迪",
          grade: "2019",
          pinyin: "ZhangTianAi",
          college: "土木工程"
        },
        {
          name: "沙溢",
          grade: "2016",
          pinyin: "ZhangTianAi",
          college: "音乐学院"
        },
        {
          name: "小明",
          grade: "2019",
          pinyin: "ZhangTianAi",
          college: "商学院"
        },
        {
          name: "小红",
          grade: "2019",
          pinyin: "ZhangTianAi",
          college: "土木工程"
        },
        {
          name: "刘德华",
          grade: "2016",
          pinyin: "ZhangTianAi",
          college: "商学院"
        },
        {
          name: "章金莱",
          grade: "2019",
          pinyin: "ZhangTianAi",
          college: "水利学院"
        },
        {
          name: "花无缺",
          grade: "2019",
          pinyin: "ZhangTianAi",
          college: "音乐学院"
        },
        {
          name: "六小龄童",
          grade: "2016",
          pinyin: "ZhangTianAi",
          college: "新闻传播学院"
        },
        {
          name: "范玮琪",
          grade: "2016",
          pinyin: "ZhangTianAi",
          college: "水利学院"
        },
        {
          name: "范冰冰",
          grade: "2019",
          pinyin: "ZhangTianAi",
          college: "音乐学院"
        },
        {
          name: "李冰冰",
          grade: "2019",
          pinyin: "ZhangTianAi",
          college: "水利学院"
        }
      ]
    };
  },
  computed: {
    filterList() {
      return this.personList.filter(person => {
        return (
          (person.college == this.selectedCollege ||
            this.selectedCollege === "全部") &&
          (person.grade == this.selectEdGrade || this.selectEdGrade === "全部")
        );
      });
    }
  },
  methods: {
    selectGrade(item) {
      this.selectEdGrade = item;
    },
    selectCollege(item) {
      this.selectedCollege = item;
    }
  }
};
</script>

<style lang="scss" scoped>
.person-list {
  background: #fff;
  border-radius: 4px;
  box-shadow: 4px 4px 40px rgba(0, 0, 0, 0.05);
  font-size: 12px;
  .divide {
    width: 100%;
    border-bottom: 1px solid #ddd;
  }
  .divide-middle {
    width: 100%;
    border-bottom: 1px solid #ebeef5;
  }
  header {
    font-weight: 400;
    padding: 8px;
  }
  .filter {
    .grade,
    .college {
      padding: 8px;
    }
    .filterItems {
      margin-right: 18px;
      cursor: pointer;
    }
    .active {
      color: rgb(100, 217, 214);
    }
  }
  .containter {
    padding: 26px 16px 16px;

    min-height: 300px;
  }
}
</style>