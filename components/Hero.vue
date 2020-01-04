<template>
  <div class="hero">
    <img class="hero--image" src="@/assets/images/denis_lg.jpeg" />
    <div class="hero--text-container">
        <div class="hero--title">
            <span>{{$t('home.welcomeMessage')}}</span>
            <div class="hero--description">{{$t('home.downloadResume')}}<i class="fas fa-arrow-circle-down"></i></div>
            </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Hero"
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
  }
  .hero--text-container {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;

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
        @include header_dark;

        span {
            word-break: break-word;
        }

        .hero--description {
            margin-top: 10px;
            font-size: 15px;
            font-family: "Quicksand", serif;
            font-weight: 500;

            i {
                margin-left: 5px;
            }
        }

    }

  }
}
</style>