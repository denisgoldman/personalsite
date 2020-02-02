<template>
  <div class="Content">
    <Hero :title="$t('home.welcomeMessage')" :description="$t('home.downloadResume')" image="anotherdenis_smol.png"/>
    <Skills/>
    <Projects/>
  </div>
</template>

<script>
import Hero from "@/components/Hero"
import ProjectsPreview from "@/components/ProjectsPreview"
import Skills from "@/components/Skills"
import Projects from "@/components/Projects"

export default {
  head () {
    return { title: this.$t('head.title') }
  },
  components: {
    Hero,
    ProjectsPreview,
    Skills,
    Projects
  }
}
</script>
