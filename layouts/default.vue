<template>
  <div class="app">
    <AppHeader />
    <div class="content">
    <Nuxt />
    </div>
  </div>
</template>

<script>
import AppHeader from "../components/AppHeader"
export default {
  components: {
    AppHeader
  }
}
</script>

<style lang="scss">
  .content {
    padding: $header_height 20px 0 20px;
  }
</style>
