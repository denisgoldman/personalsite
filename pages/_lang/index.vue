<template>
  <div class="Content">
    <Hero/>
  </div>
</template>

<script>
import Hero from "@/components/Hero"

export default {
  head () {
    return { title: this.$t('head.title') }
  },
  components: {
    Hero
  }
}
</script>
