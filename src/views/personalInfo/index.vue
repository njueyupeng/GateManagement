<template>
  <div class="app-container">
    <div v-if="user">
      <el-row :gutter="20">
        <el-col :span="6" :xs="24">
          <user-card :user="user" />
        </el-col>

        <el-col :span="18" :xs="24">
          <el-card>
            <el-tabs v-model="activeTab">
              <el-tab-pane label="可控房间" name="activity">
                <activity />
              </el-tab-pane>
              <el-tab-pane label="可控设备" name="equipemnt">
                <Equipment />
              </el-tab-pane>
              <el-tab-pane label="权限审核" name="access">
                <span slot="label">
                  <span>
                    权限审核
                    <el-badge :value="4" class="item" style="position:relative;left:-2px"></el-badge>
                  </span>
                </span>
                <Access />
              </el-tab-pane>
            </el-tabs>
          </el-card>
        </el-col>
      </el-row>
    </div>
  </div>
</template>

<script>
import { mapGetters } from "vuex";
import UserCard from "./components/UserCard";
import Activity from "./components/Activity";
import Equipment from "./components/Equipment";
import Access from "./components/Access";

export default {
  name: "Profile",
  components: {
    UserCard,
    Activity,
    Equipment,
    Access
    //   Timeline, Account
  },
  data() {
    return {
      user: {},
      activeTab: "activity"
    };
  },
  computed: {
    // ...mapGetters([
    //   'name',
    //   'avatar',
    //   'roles'
    // ])
  },
  created() {
    // this.getUser()
  },
  methods: {
    // getUser() {
    //   this.user = {
    //     name: this.name,
    //     role: this.roles.join(' | '),
    //     email: 'admin@test.com',
    //     avatar: this.avatar
    //   }
    // }
  }
};
</script>

<style lang="scss" scoped>
.app-container {
  background: white;
}
</style>