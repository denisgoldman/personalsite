<template>
  <div class="projects--container">
    <div class="projects--container--title-container">
      <h1 class="projects--title dm">{{$t('projects.previewTitle')}}</h1>
    </div>
    <div class="projects--container--cards">
      <ProjectCard :title="('Amazing project')" :description="('Cool stuff')" image="preview.jpeg" />
      <ProjectCard
        :title="('Amazing project 2')"
        :description="('Cool stuff')"
        image="preview.jpeg"
      />
      <ProjectCard
        :title="('Amazing project 3')"
        :description="('Cool stuff')"
        image="preview.jpeg"
      />
      <ProjectCard
        :title="('Amazing project 4')"
        :description="('Cool stuff')"
        image="preview.jpeg"
      />
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
    //grid-template-columns: repeat(1, 1fr);
    grid-gap: 1.333rem;
    @media (min-width: $layout_width) {
      grid-gap: 0;
    }
    @media (min-width: $breakpoint_mobile) {
      //grid-template-columns: repeat(2, 1fr);
    }
  }
  .projects--container--title-container {
    //text-align: center;
    .projects--title {
      padding: 20px;
    }
  }
}
</style>