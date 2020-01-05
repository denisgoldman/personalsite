<template>
  <div class="projects--container">
    <div class="projects--container--title-container">
      <h2 class="projects--title">{{$t('projects.previewTitle')}}</h2>
    </div>
    <div class="projects--container--cards">
    <ProjectCard :title="('Amazing project')" :description="('Cool stuff')" image="preview.jpeg" />
    <ProjectCard :title="('Amazing project 2')" :description="('Cool stuff')" image="preview.jpeg" />
    <ProjectCard :title="('Amazing project 3')" :description="('Cool stuff')" image="preview.jpeg" />
    </div>
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
  padding: 0 20px;
  @media (min-width: $layout_width) {
    padding: 0;
  }
  .projects--container--cards {
    display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  grid-gap: 1.333rem;
  @media (min-width: $layout_width) {
    grid-gap: 3rem;
  }
  }
  .projects--container--title-container {
    text-align: center;
    .projects--title {
      padding: 20px;
    }
  }
}
</style>