<template>
  <d2-container :filename="filename">
    <template slot="header">一般</template>
    <div class="inner">
      <ve-map :data="chartData" v-bind="pubSetting" :settings="chartSettings"></ve-map>
    </div>
    <template slot="footer">
      <d2-link-btn title="更多示例和文档" link="https://v-charts.js.org"/>
    </template>
  </d2-container>
</template>

<script>
import list from '@/pages/demo/charts/list/_mixin/list.js'
import mapOrigin from '@/pages/demo/charts/list/_data/china'
export default {
  mixins: [
    list
  ],
  data () {
    return {
      chartSettings: {
        mapOrigin
      },
      filename: __filename,
      chartData: {
        columns: ['位置', '税收', '人口', '面积'],
        rows: [
          { '位置': '吉林', '税收': 123, '人口': 123, '面积': 92134 },
          { '位置': '北京', '税收': 1223, '人口': 2123, '面积': 29234 },
          { '位置': '上海', '税收': 2123, '人口': 1243, '面积': 94234 },
          { '位置': '浙江', '税收': 4123, '人口': 5123, '面积': 29234 }
        ]
      }
    }
  }
}
</script>

<style lang="scss" scoped>
.inner {
  position: absolute;
  top: 20px;
  right:  20px;
  bottom: 20px;
  left: 20px;
}
</style>
