<template>
  <div class="Content">
    <Hero :title="$t('home.welcomeMessage')" :description="$t('home.downloadResume')" image="anotherdenis_smol.png"/>
    <Skills/>
    <ProjectsPreview/>
  </div>
</template>

<script>
import Hero from "@/components/Hero"
import ProjectsPreview from "@/components/ProjectsPreview"
import Skills from "@/components/Skills"

export default {
  head () {
    return { title: this.$t('head.title') }
  },
  components: {
    Hero,
    ProjectsPreview,
    Skills
  }
}
</script>
