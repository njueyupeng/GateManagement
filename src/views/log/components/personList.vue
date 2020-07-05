<template>
  <div class="equipment-list">
    <header>日志列表</header>
    <div class="divide"></div>
    <div class="filter">
      <div class="grade">
        <span
          v-for="(item,index) in logTypeList"
          :key="index"
          :class="{active:selectedType===item}"
          class="filterItems"
          @click="selectType(item)"
        >{{item}}</span>
      </div>
      <div class="divide-middle"></div>
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
      <div class="grade">
        <span
          v-for="(item,index) in buildingList"
          :key="index"
          :class="{active:selectedBuilding===item}"
          class="filterItems"
          @click="selectBuilding(item)"
        >{{item}}</span>
      </div>
      <div class="divide-middle"></div>
    </div>
    <div class="containter">
      <el-table  border :data="tableData" style="width: 100%">
        <el-table-column prop="name" label="人员" width="180"></el-table-column>
        <el-table-column prop="id" label="学号" width="180"></el-table-column>
        <el-table-column prop="eId" label="设备编号"></el-table-column>
        <el-table-column prop="eType" label="设备类型"></el-table-column>
        <el-table-column prop="optionType" label="操作类型"></el-table-column>
        <el-table-column prop="optionTime" label="操作时间"></el-table-column>
      </el-table>
      <div v-if="filterList.length===0">空</div>
      <div style="clear:both"></div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      logTypeList: ["房间日志", "设备日志"],
      buildingList: [
        "全部",
        "一号楼",
        "二号楼",
        "三号楼",
        "四号楼",
        "五号楼",
        "六号楼",
        "七号楼",
        "八号楼",
        "九号楼"
      ],
      gradeList: ["全部", "东校区", "西校区", "南校区", "北校区", "莲花路校区"],
      selectEdGrade: "全部",
      selectedType: "房间日志",
      selectedBuilding: "全部",
      selectedCollege: "全部",
      collegeList: [
        "全部",
        "体育馆",
        "教学楼",
        "实验楼",
        "宿舍楼",
        "艺术设计楼",
        "行政楼",
        "游泳馆"
      ],
      equipmentList: [
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
      ],
      tableData: [
        {
          name: "赵思伟",
          id: "2121012",
          eId: "10172",
          eType: "空调",
          optionType: "解绑",
          optionTime: "2020-07-01 21:00:00",
        },
        {
          name: "赵思伟",
          id: "2121012",
          eId: "10172",
          eType: "空调",
          optionType: "解绑",
          optionTime: "2020-07-01 21:00:00",
        },
        {
          name: "赵思伟",
          id: "2121012",
          eId: "10172",
          eType: "空调",
          optionType: "解绑",
          optionTime: "2020-07-01 21:00:00",
        },
        {
          name: "赵思伟",
          id: "2121012",
          eId: "10172",
          eType: "空调",
          optionType: "解绑",
          optionTime: "2020-07-01 21:00:00",
        },
        {
          name: "赵思伟",
          id: "2121012",
          eId: "10172",
          eType: "空调",
          optionType: "解绑",
          optionTime: "2020-07-01 21:00:00",
        },
        {
          name: "赵思伟",
          id: "2121012",
          eId: "10172",
          eType: "空调",
          optionType: "解绑",
          optionTime: "2020-07-01 21:00:00",
        },
        {
          name: "赵思伟",
          id: "2121012",
          eId: "10172",
          eType: "空调",
          optionType: "解绑",
          optionTime: "2020-07-01 21:00:00",
        },
        {
          name: "赵思伟",
          id: "2121012",
          eId: "10172",
          eType: "空调",
          optionType: "解绑",
          optionTime: "2020-07-01 21:00:00",
        },
        {
          name: "赵思伟",
          id: "2121012",
          eId: "10172",
          eType: "空调",
          optionType: "解绑",
          optionTime: "2020-07-01 21:00:00",
        },
        {
          name: "赵思伟",
          id: "2121012",
          eId: "10172",
          eType: "空调",
          optionType: "解绑",
          optionTime: "2020-07-01 21:00:00",
        },
       
      ]
    };
  },
  computed: {
    filterList() {
      return this.equipmentList.filter(equipment => {
        return (
          (equipment.college == this.selectedCollege ||
            this.selectedCollege === "全部") &&
          (equipment.grade == this.selectEdGrade ||
            this.selectEdGrade === "全部")
        );
      });
    }
  },
  methods: {
    selectGrade(item) {
      this.selectEdGrade = item;
    },
    selectType(item) {
      this.selectedType = item;
    },
    selectBuilding(item) {
      this.selectedBuilding = item;
    },
    selectCollege(item) {
      this.selectedCollege = item;
    }
  }
};
</script>

<style lang="scss" scoped>
.equipment-list {
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