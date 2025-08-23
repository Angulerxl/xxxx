<template>
  <div>
    <Lock @login="login" v-if="!islock" />
    <el-tabs v-else v-model="activeName" type="card" @tab-click="handleClick">
      <el-tab-pane label="店小秘" name="first">
        <div>准备开始</div>
      </el-tab-pane>
      <!-- <el-tab-pane label="独立站店小秘" name="first">
        <Sys3Home />
      </el-tab-pane> -->
      <!-- <el-tab-pane label="虾皮店小秘" name="second">
        <Sys2Home />
      </el-tab-pane>
      <el-tab-pane label="旧系统" name="third">
        <Main />
      </el-tab-pane> -->
    </el-tabs>

  </div>
</template>

<script>
import Main from "./Main.vue";
import Lock from "./Lock.vue";

export default {
  name: "Home",
  components: {
    Lock,
  },
  mounted() {},
  data: () => {
    return {
      islock: sessionStorage.getItem("isShopLock"),
      activeName: "first",
    };
  },
  methods: {
    login(bol) {
      this.islock = bol;
    },
    handleClick() {},
  },
};
</script>
<style lang="less" scoped>
:deep(.el-tabs__content) {
  height: calc(100vh - 60px);
  overflow-y: auto;
}
</style>
