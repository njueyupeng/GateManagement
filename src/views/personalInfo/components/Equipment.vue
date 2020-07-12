<template>
  <div class="user-activity">
    <div class="post">
      <div>
        <el-table :data="tableData" style="width: 100%">
          <el-table-column prop="name" label="设备列表"></el-table-column>
          <el-table-column width="80">
            <el-button size="mini">查看</el-button>
          </el-table-column>
        </el-table>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      tableData: [
        {
          date: "2016-05-02",
          name: "智能门锁",
          address: "上海市普陀区金沙江路 1518 弄"
        },
        {
          date: "2016-05-04",
          name: "空调",
          address: "上海市普陀区金沙江路 1517 弄"
        },
        {
          date: "2016-05-01",
          name: "电控开关",
          address: "上海市普陀区金沙江路 1519 弄"
        },
        {
          date: "2016-05-03",
          name: "智能垃圾桶",
          address: "上海市普陀区金沙江路 1516 弄"
        }
      ]
    };
  }
};
</script>

<style lang="scss" scoped>
.user-activity {
  .user-block {
    .username,
    .description {
      display: block;
      margin-left: 50px;
      padding: 2px 0;
    }

    .username {
      font-size: 16px;
      color: #000;
    }

    :after {
      clear: both;
    }

    .img-circle {
      border-radius: 50%;
      width: 40px;
      height: 40px;
      float: left;
    }

    span {
      font-weight: 500;
      font-size: 12px;
    }
  }

  .post {
    font-size: 14px;
    border-bottom: 1px solid #d2d6de;
    margin-bottom: 15px;
    padding-bottom: 15px;
    color: #666;

    .image {
      width: 100%;
      height: 100%;
    }

    .user-images {
      padding-top: 20px;
    }
  }

  .list-inline {
    padding-left: 0;
    margin-left: -5px;
    list-style: none;

    li {
      display: inline-block;
      padding-right: 5px;
      padding-left: 5px;
      font-size: 13px;
    }

    .link-black {
      &:hover,
      &:focus {
        color: #999;
      }
    }
  }
}

.box-center {
  margin: 0 auto;
  display: table;
}

.text-muted {
  color: #777;
}
</style>
