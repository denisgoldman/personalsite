<template>
  <div class="hero">
    <img class="hero--image" :src="require(`@/assets/images/heroes/${image}`)" />
    <div class="hero--text-container">
      <div class="hero--title">
        <h2>{{title}}</h2>
        <!-- <div class="hero--description">
          <span>{{description}}</span>
          <i class="fas fa-arrow-circle-down"></i>
        </div> -->
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
  height: 600px;
  position: relative;
  background: #fff;
  @media (prefers-color-scheme: dark) {
    background: $areaColor_dark;
  }
  @media (max-width: $breakpoint_mobile) {
      height: auto;
  }
  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
    @media (max-width: $breakpoint_mobile) {
      height: 50%;
      min-height: 250px;
    }
    @media (prefers-color-scheme: dark) {
      filter: grayscale(1) brightness(1.1);
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
      height: auto;
      text-align: center;
    }

    .hero--title {
      position: absolute;
      right: 0;
      top: 50%;
      transform: perspective(1px) translateY(-50%);
      padding: 20px 60px 30px 30px;
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
        padding: 20px;
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

        @media (max-width: $breakpoint_mobile) {
            margin-top: 20px;
        }

        span {
          transition: all 0.3s;
          & + i {
            transition: all 0.3s;
          }
        }

        span:hover {
          cursor: pointer;
          color: $colorGold;
          transition: all 0.3s;
          // @include gradient_sunset;
          // -webkit-text-fill-color: transparent;
          // box-decoration-break: clone;
          // background-clip: text;
          & + i {
            color: $colorGold;
            transition: all 0.3s;
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