<template lang="pug">
.main-content
  el-card.each-card
    .each-item
      .left
        .title 热门
      .right
        .content(
          v-for="(eachUrl, urlIndex) in Hot"
          :index="urlIndex"
        )
          el-link(:href="eachUrl.url" target="_blank") {{ eachUrl.name }}
  el-card.each-card
    .each-item(
      v-for="(category, index) in URL_LIST"
      :key="index"
    )
      .left
        .title {{ category.type }}
      .right
        .content(
          v-for="(eachUrl, urlIndex) in category.data"
          :key="urlIndex"
        )
          el-link(:href="eachUrl.url" target="_blank") {{ eachUrl.name }}

</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import { URL_LIST, Hot } from '@/config';

@Component({
  data() {
    return {
      URL_LIST,
      Hot,
    };
  },
})
export default class Home extends Vue {}
</script>

<style lang="less" scoped>
.each-item {
  border-bottom: 1px dotted #eee;
  padding: 16px;
  display:flex;
  flex-direction: row;
  align-items: flex-start;
}
.left {
  width: 120px;
  text-align: left;
}
.right {
  display: flex;
  flex: 1;
  flex-direction: row;
  flex-wrap: wrap;
  align-items: center;
}

.content {
  width: 120px;
  text-align: left;
}

.title {
  color: #333;
  font-size: 14px;
  font-weight: 500;
}

.each-card {
  margin: 16px 0;
}
</style>
