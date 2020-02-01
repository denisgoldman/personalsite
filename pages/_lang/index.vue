<template>
  <div class="Content">
    <Hero :title="$t('home.welcomeMessage')" :description="$t('home.downloadResume')" image="anotherdenis_smol.png"/>
    <ProjectsPreview/>
  </div>
</template>

<script>
import Hero from "@/components/Hero"
import ProjectsPreview from "@/components/ProjectsPreview"

export default {
  head () {
    return { title: this.$t('head.title') }
  },
  components: {
    Hero,
    ProjectsPreview
  }
}
</script>
