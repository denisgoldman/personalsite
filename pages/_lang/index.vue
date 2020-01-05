<template>
  <div class="Content">
    <Hero :title="$t('home.welcomeMessage')" :description="$t('home.downloadResume')" image="denis_lg.jpeg"/>
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
