<template>
  <div class="projects--container">
    <div class="projects--container--title-container">
      <div class="projects--title">{{$t('projects.previewTitle')}}</div>
    </div>
    <ProjectCard image="preview.jpeg" />
  </div>
</template>

<script>
import ProjectCard from "@/components/ProjectCard";

export default {
  name: "ProjectsPreview",
  components: {
    ProjectCard
  }
};
</script>

<style lang="scss">
.projects--container {
  .projects--container--title-container {
    text-align: center;
    .projects--title {
      font-family: "Quicksand", serif;
      font-weight: 700;
      font-size: 30px;
      padding: 20px;
    }
  }
}
</style>