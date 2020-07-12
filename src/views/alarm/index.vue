<template>
  <div class="alarm-container">
    <div class="option">
      <!-- 名称 -->
      <el-input v-model="search.name" style="width:200px" placeholder="请输入告警名称"></el-input>
      <!-- 时间 -->
      <!-- <el-date-picker v-model="startTime" style="width:200px" type="datetime" placeholder="选择日期时间"></el-date-picker> -->
      <!-- 告警类型 -->
      <el-select v-model="search.type" placeholder="请选择告警类型">
        <el-option
          v-for="item in alarmOptions"
          :key="item.value"
          :label="item.label"
          :value="item.value"
        ></el-option>
      </el-select>
      <!-- 查询 -->
      <el-button type="primary" icon="el-icon-search">查询</el-button>
      <!-- 新增告警 -->
      <el-button type="primary" style="float:right">
        <svg-icon icon-class="add" style="margin-right:6px" />新增告警规则
      </el-button>
    </div>
    <div class="tableBox">
      <el-table :data="tableData" border style="width: 100%">
        <el-table-column prop="name" label="告警名称" width="180"></el-table-column>
        <el-table-column prop="alarmType" label="告警类型" width="180"></el-table-column>
        <el-table-column prop="startTime" label="开始时间" width="180"></el-table-column>
        <el-table-column prop="noticeType" label="通知类型"></el-table-column>
        <el-table-column fixed="right" label="操作" width="160">
          <template slot-scope="scope">
            <el-button @click="handleEdit(scope.row)" type="primary" size="small">编辑</el-button>
            <el-button type="danger" size="small">删除</el-button>
          </template>
        </el-table-column>
      </el-table>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";

export default {
  name: "Alarm",
  data() {
    return {
      search: {
        name: "",
        startTime: null,
        type: ""
      },
      alarmOptions: [{ value: "1", label: "非正常时段开门" }],
      tableData: [
        {
          startTime: "2020-05-02 18:00:00",
          name: "东校区三号楼",
          noticeType: "短信、APP",
          alarmType: "非正常时段开门",
          id: 1
        },
        {
          startTime: "2020-05-02 18:00:00",
          name: "东校区三号楼",
          noticeType: "短信、APP",
          alarmType: "非正常时段开门",
          id: 1
        },
        {
          startTime: "2020-05-02 18:00:00",
          name: "东校区三号楼",
          noticeType: "短信、APP",
          alarmType: "非正常时段开门",
          id: 1
        },
        {
          startTime: "2020-05-02 18:00:00",
          name: "东校区三号楼",
          noticeType: "短信、APP",
          alarmType: "非正常时段开门",
          id: 1
        },
        {
          startTime: "2020-05-02 18:00:00",
          name: "东校区三号楼",
          noticeType: "短信、APP",
          alarmType: "非正常时段开门",
          id: 1
        },
        {
          startTime: "2020-05-02 18:00:00",
          name: "东校区三号楼",
          noticeType: "短信、APP",
          alarmType: "非正常时段开门",
          id: 1
        },
        {
          startTime: "2020-05-02 18:00:00",
          name: "东校区三号楼",
          noticeType: "短信、APP",
          alarmType: "非正常时段开门",
          id: 1
        }
      ]
    };
  },
  methods: {
    handleEdit(row) {}
  }
};
</script>

<style lang="scss" scoped>
.alarm-container {
  background: white;
  padding: 16px;
  min-height: 600px;
  .option {
  }
  .tableBox {
    margin-top: 30px;
  }
}
</style>
