<template>
  <div class="page-indicator">
    <h1 class="page-title">Indicator</h1>
    <div class="page-indicator-wrapper">
      <mt-button @click.native="openIndicator" size="large">点击弹出 Indicator</mt-button>
      <mt-button @click.native="openIndicatorWithSpinner" size="large">可配置 spinner</mt-button>
      <mt-button @click.native="openIndicatorWithText" size="large">点击弹出带有文字的 Indicator</mt-button>
    </div>
  </div>
</template>

<script>
import { Indicator } from 'mint-ui'
export default {
  name: 'Loading',
  methods: {
    openIndicator () {
      Indicator.open()
      setTimeout(() => Indicator.close(), 2000)
    },

    openIndicatorWithSpinner () {
      Indicator.open({ spinnerType: 'fading-circle' })
      setTimeout(() => Indicator.close(), 2000)
    },

    openIndicatorWithText () {
      Indicator.open('加载中...')
      setTimeout(() => Indicator.close(), 2000)
    }
  },

  beforeDestroy () {
    Indicator.close()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
button {
  margin-bottom: 20px;
}
.page {
  &-indicator {
    &-wrapper {
      padding: 0 20px;
      position: absolute;
      width: 100%;
    }
  }
}
</style>
