<template>
  <div class="project-card--container">
    <div class="project-card">
        <div class="project-card--image-container">
          <img class="project-card--image-container--image" :src="require(`@/assets/images/projects/previews/${image}`)" />
        </div>
       
      <div class="project-card--content-container">
          <div class="project-card--content-container--subtitle">{{description}}</div>
          <div class="project-card--content-container--title">{{title}}</div>
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
//   padding: 0 20px;

  .project-card {
    display: flex;
    flex-grow: 1;
    flex-direction: column;
    max-width: 100%;
    box-sizing: border-box;
    position: relative;
    background: #fff;
    overflow: hidden;
    @media (prefers-color-scheme: dark) {
        background: #222;
    }
    .project-card--image-container {
      position: relative;
      width: 100%;
      padding-bottom: 100%;
      float: left;
      height: 0;
      .project-card--image-container--image {
        width: 100%;
        height: 100%;
        position: absolute;
        left: 0;
        object-fit: cover;
      }
    }
    .project-card--content-container {
        padding: 24px;
        .project-card--content-container--subtitle {
            font-size: 14px;
            font-family: "Quicksand", serif;
            font-weight: 500;
            margin-bottom: 10px;
        }
        .project-card--content-container--title {
            font-size: 20px;
            font-family: "Quicksand", serif;
            font-weight: 700;
        }
    }
  }
}
</style>