<template>
  <div class="project-card--container">
    <div class="project-card">
        <div class="project-card--image-container">
          <img class="project-card--image-container--image" :src="require(`@/assets/images/projects/previews/${image}`)" />
        </div>
       
      <div class="project-card--content-container">
          <h3 class="project-card--content-container--title">{{title}}</h3>
          <div class="project-card--content-container--subtitle">{{description}}</div>
        </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "ProjectCard",
  props: {
    title: {
      type: String
    },
    description: {
      type: String
    },
    image: {
      type: String
    }
  }
};
</script>

<style lang="scss">
.project-card--container {
border: 5px solid transparent;

  .project-card {
    display: -webkit-box;
    height: 100%;
    flex-direction: column;
    overflow: hidden;
    @media (prefers-color-scheme: dark) {
        background: $areaColor_dark;
    }
    .project-card--image-container {
      flex-grow: 1;
      display: flex;
      .project-card--image-container--image {
        width: 100%;
        object-fit: cover;
      }
    }
    .project-card--content-container {
        padding: 15px 20px 20px 30px;
        .project-card--content-container--subtitle {
            font-size: 1.2rem;
            font-family: "Quicksand", serif;
            font-weight: 500;
            color: $secondaryTextColor;
        }
        .project-card--content-container--title {
            margin-bottom: 5px;
        }
    }
  }
}
</style>