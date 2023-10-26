<template>
  <div class="default-layout">
    <div class="default-layout__header">
      <default-header/>
    </div>
    <div class="default-layout__content">
      <router-view/>
    </div>
  </div>
</template>

<script setup>
import DefaultHeader from '@/components/common/defaultLayout/DefaultHeader'
</script>

<style lang="scss" scoped>
.default-layout {

}
</style>
