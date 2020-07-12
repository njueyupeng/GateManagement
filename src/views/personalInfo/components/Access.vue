<template>
  <div class="user-activity">
    <div class="post">
      <div>
        <el-table :data="tableData" style="width: 100%">
          <el-table-column prop="name" label="申请人"></el-table-column>
          <el-table-column prop="id" label="申请人ID"></el-table-column>
          <el-table-column prop="contain" label="申请项目"></el-table-column>
          <el-table-column width="160">
            <el-button size="mini" type="primary">同意</el-button>
            <el-button size="mini" type="danger">驳回</el-button>
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
          name: "张三",
          id: "2120121925",
          contain: "教学楼101闸机权限"
        },
        {
          name: "李四",
          id: "2120121925",
          contain: "教学楼101闸机权限"
        },
        {
          name: "佳佳",
          id: "2120121925",
          contain: "教学楼101闸机权限"
        },
        {
          name: "孙二",
          id: "2120121925",
          contain: "教学楼101闸机权限"
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
