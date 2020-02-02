<template>
<div class="projects">
    <div class="projects__header">
        <h2>{{$t('projects.title')}}</h2>
        <h4 class="projects__subtitle">{{$t('projects.subtitle')}}</h4>
    </div>
  <div class="grid">
      <ProjectCard class="span-3" :title="($t('projects.rolex.title'))" :description="($t('projects.rolex.subtitle'))" image="rolexpackagingsolid.jpg" />
      <!-- <ProjectCard class="span-1" :title="('Amazing project')" :description="('Cool stuff')" image="preview.jpeg" /> -->
      <!-- <ProjectCard class="span-2" :title="('Amazing project')" :description="('Cool stuff')" image="preview.jpeg" /> -->
      <!-- <ProjectCard class="span-3" :title="('Amazing project')" :description="('Cool stuff')" image="preview.jpeg" /> -->
  </div>
  </div>
</template>

<script>
import ProjectCard from "@/components/ProjectCard";
export default {
    name: "Projects",
    components: {
    ProjectCard
  }
}
</script>

<style lang="scss">

    .projects {
        margin: 0 -5px;
        &__header {
            padding: 20px 20px 40px 20px;
            margin-bottom: -5px;
            text-align: center;
            background: $areaColor_light;
            @media(prefers-color-scheme: dark) {
                background: $areaColor_dark;
            }
        }

        &__subtitle {
             @media (prefers-color-scheme: dark) {
          color: $secondaryTextColor;
      }
        }
    }

    .grid {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        grid-auto-rows: 750px;

        .span-1 {
            grid-column: span 1;
        }
        .span-2 {
            grid-column: span 2;
        }
        .span-3 {
            grid-column: span 3;
        }
    }
</style>