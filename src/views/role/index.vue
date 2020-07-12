<template>
  <div class="role-cotainer">
    <div class="roleList">
      <div class="title">角色列表</div>
      <el-button type="primary" class="addBtn" size="mini" @click="addRole">添加</el-button>
      <div class="roleBox">
        <div
          class="role"
          :class="{selectedRole:role.id===selectedRole.id}"
          v-for="(role,index) in roleList"
          :key="index"
          @click="doSelect(role)"
        >
          <i class="el-icon-user-solid" />
          {{role.name}}
          <i class="el-icon-arrow-right rightIcon" />
        </div>
      </div>
    </div>
    <div class="accessBox">
      <access-box :role="selectedRole" />
    </div>
  </div>
</template>

<script>
import accessBox from "./access";
export default {
  components: { accessBox },
  data() {
    return {
      selectedRole: {
        id: 1,
        name: "总管理员",
        access: [1, 2, 3, 4, 5, 6, 7]
      },
      roleList: [
        {
          id: 1,
          name: "总管理员",
          access: [1, 2, 3, 4, 5, 6, 7]
        },
        {
          id: 2,
          name: "普通访客",
          access: [1, 2, 3]
        }
      ]
    };
  },
  computed: {
    currentRole() {}
  },
  methods: {
    doSelect(role) {
      this.selectedRole = role;
    },
    addRole() {}
  }
};
</script>

<style lang="scss" scoped>
.role-cotainer {
  background: white;
  min-height: 600px;
  display: flex;
  .roleList {
    width: 300px;
    border-right: 1px solid #ddd;
    padding-top: 16px;
    position: relative;
    .title {
      font-size: 18px;
      font-weight: 500;
      padding-left: 16px;
    }
    .addBtn {
      position: absolute;
      top: 10px;
      right: 26px;
    }
    .roleBox {
      margin-top: 20px;
      .rightIcon {
        color: white;
        position: absolute;
        right: 10px;
        font-size: 16px;
      }
      .role {
        position: relative;
        padding: 10px 16px;
        font-size: 14px;
        &:hover {
          background: #eee;
          cursor: pointer;
        }
        border-top: 1px so lid #ddd;
        border-bottom: 1px so lid #ddd;
      }
      .selectedRole {
        background: #409eff !important;
        .rightIcon {
          color: black;
        }
      }
    }
  }
  .accessBox {
    width: 100%;
  }
}
</style>