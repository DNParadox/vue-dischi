<template>
  <div id="app">
    <DiskHeader />
    <DiskMain />


  </div>
</template>

<script>

import DiskHeader from './components/DiskHeader.vue'
import DiskMain from './components/DiskMain.vue'

export default {
  name: 'App',
  components: {
    DiskHeader,
    DiskMain


  }
}
</script>

<style lang="scss">
@import './style/common.scss'
</style>
