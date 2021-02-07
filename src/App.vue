<template lang="pug">
#app
  el-container
    el-header
      el-menu(
        mode="horizontal"
        :default-active="activeIndex"
        @select="handleSelect"
      )
        el-menu-item(index="Home") 首页
      .page-title 程序员导航
    el-main
      <router-view/>
    el-footer
        el-link(:underline="false" href="https://github.com/novaalone/ProgrammerNav/issues" target="_blank").link-text 反馈建议
        el-link(:underline="false" href="/pay").link-text 友情赞助
        el-link(:underline="false" href="mailto:novafighting@163.com").link-text 官方合作
        el-link(:underline="false").link-text 交个朋友
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class App extends Vue {
  private activeIndex = 'Home';

  private handleSelect(key: string) {
    this.$router.push({
      name: key,
    });
  }
}
</script>

<style lang="less">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #333;
}

.el-header {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: center;
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  height: 50px;
}

.el-main {
  padding-top: 80px;
  min-height: 600px;
}
.el-footer {
  padding: 0;
  position: fixed;
  bottom: 0;
  left:0;
  right: 0;
  padding: 40px;
  background:  #3F4C5F;
  display: flex;
  flex-direction: row;
  justify-content: flex-start;
  align-items: center;
}

.link-text {
  font-size: 16px;
  font-weight: 500;
  width: 100px;

  &.el-link.el-link--default {
    color:#fff;
  }
}

.page-title {
  font-size: 18px;
  color:#333;
  font-weight: 500;
}
</style>
