<template>
  <div class="hero">
    <img class="hero--image" :src="require(`@/assets/images/${image}`)" />
    <div class="hero--text-container">
      <div class="hero--title">
        <span>{{title}}</span>
        <div class="hero--description">
          <span>{{description}}</span>
          <i class="fas fa-arrow-circle-down"></i>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Hero",
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
.hero {
  max-width: $layout_width;
  height: 500px;
  position: relative;
  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    @media (max-width: $breakpoint_mobile) {
      height: 50%;
    }
  }
  .hero--text-container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;

    @media (max-width: $breakpoint_mobile) {
      position: relative;
    }

    .hero--title {
      position: absolute;
      right: 0;
      top: 50%;
      transform: perspective(1px) translateY(-50%);
      padding: 20px;
      font-family: "Quicksand", serif;
      font-weight: 700;
      font-size: 30px;
      max-width: 40%;
      color: #000;
      @include blurred-background_light;

      @media (prefers-color-scheme: dark) {
        color: #fff;
        @include blurred-background_dark;
      }

      @media (max-width: $breakpoint_mobile) {
        position: relative;
        right: auto;
        top: auto;
        transform: none;
        max-width: 100%;
        background: none;
      }

      span {
        word-break: break-word;
      }

      .hero--description {
        margin-top: 10px;
        font-size: 15px;
        font-family: "Quicksand", serif;
        font-weight: 500;
        color: #222;

        @media (prefers-color-scheme: dark) {
          color: #fff;
        }

        span:hover {
          cursor: pointer;
          @include gradient_sunset;
          -webkit-text-fill-color: transparent;
          box-decoration-break: clone;
          background-clip: text;
          & + i {
            color: #ff6a00;
          }
        }

        i {
          color: #222;
          @media (prefers-color-scheme: dark) {
            color: #fff;
          }
        }
      }
    }
  }
}
</style>