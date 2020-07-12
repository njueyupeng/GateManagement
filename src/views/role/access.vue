<template>
  <div class="accessBox">
    <div>角色名称:{{role.name}}</div>
    <div style="margin-top:20px;margin-bottom:16px;">角色权限:</div>
    <el-table border :data="tableData" style="width: 100%">
      <el-table-column prop="name" label="权限名称"></el-table-column>
      <el-table-column prop="name" label="是否应有权限" width="120">
        <template slot-scope="scope">
          <i
            class="el-icon-success"
            style="color:#67C23A"
            v-if="role.access.some(item=>item===scope.row.id)"
          ></i>
          <i
            class="el-icon-error"
            style="color:#F56C6C"
            v-if="!role.access.some(item=>item===scope.row.id)"
          ></i>
        </template>
      </el-table-column>
      <el-table-column label="操作" width="120">
        <template slot-scope="scope">
          <el-button size="mini" v-if="!role.access.some(item=>item===scope.row.id)">添加权限</el-button>
          <el-button size="mini" type="danger" v-if="role.access.some(item=>item===scope.row.id)">移除权限</el-button>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>


<script>
export default {
  props: {
    role: {
      type: Object,
      default: () => ({
        access: []
      })
    }
  },
  data() {
    return {
      tableData: [
        {
          id: 1,
          name: "添加房间"
        },
        {
          id: 2,
          name: "删除房间"
        },
        {
          id: 3,
          name: "列表查看"
        },
        {
          id: 4,
          name: "修改房间"
        },
        {
          id: 5,
          name: "设置房间管理员"
        },
        {
          id: 6,
          name: "设置房间管理员"
        },
        {
          id: 7,
          name: "查看房间设备列表"
        },
        {
          id: 8,
          name: "查看房间绑定人员列表"
        },
        {
          id: 9,
          name: "查看房间绑定卡片列表"
        },
        {
          id: 10,
          name: "查看房间日志"
        },
        {
          id: 11,
          name: "房间最近日志展示"
        },
        {
          id: 12,
          name: "查看房间密码"
        },
        {
          id: 13,
          name: "添加房间密码"
        },
        {
          id: 13,
          name: "删除房间密码"
        }
      ]
    };
  },
  methods: {
    handleEdit(index, row) {
      console.log(index, row);
    },
    handleDelete(index, row) {
      console.log(index, row);
    }
  }
};
</script>

<style lang="scss" scoped>
.accessBox {
  padding: 16px;
}
</style>