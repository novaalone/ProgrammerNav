<template lang="pug">
.main-content
    .title 感谢您在我前进路上的支持，一分也是爱，我会继续努力哒！
    .pay-way
        .way
            .text 支付宝
            el-image.pay-image(:src="require('../assets/alipay.jpg')")
        .way
            .text 微信
            el-image.pay-image(:src="require('../assets/weixin.jpg')")

</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component
export default class Pay extends Vue {}
</script>

<style lang="less" scoped>
.pay-way {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: center;
    margin-top: 50px;
}

.pay-image {
    width: 240px;
    height: 240px;
}
</style>
