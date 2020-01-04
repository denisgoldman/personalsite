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
    margin: $header_height auto 0 auto;
    max-width: $layout_width;
  }
</style>
