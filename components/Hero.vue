<template>
  <div class="hero">
    <img src="@/assets/images/bentley.jpeg" />
    <div class="transparent"></div>
  </div>
</template>

<script>
export default {
  name: "Hero"
};
</script>

<style lang="scss">
@mixin gradient_light {
  background: -moz-linear-gradient(left,  rgba(255,255,255,0) 0%, rgba(255,255,255,0) 33%, rgba(255,255,255,0.51) 67%, rgba(255,255,255,1) 100%);
background: -webkit-linear-gradient(left,  rgba(255,255,255,0) 0%,rgba(255,255,255,0) 33%,rgba(255,255,255,0.51) 67%,rgba(255,255,255,1) 100%);
background: linear-gradient(to right,  rgba(255,255,255,0) 0%,rgba(255,255,255,0) 33%,rgba(255,255,255,0.51) 67%,rgba(255,255,255,1) 100%);
filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#00ffffff', endColorstr='#ffffff',GradientType=1 );

}

@mixin gradient_dark {
  background: -moz-linear-gradient(left,  rgba(255,255,255,0) 0%, rgba(129,129,129,0) 33%, rgba(0,0,0,0.51) 67%, rgba(0,0,0,1) 100%);
background: -webkit-linear-gradient(left,  rgba(255,255,255,0) 0%,rgba(129,129,129,0) 33%,rgba(0,0,0,0.51) 67%,rgba(0,0,0,1) 100%);
background: linear-gradient(to right,  rgba(255,255,255,0) 0%,rgba(129,129,129,0) 33%,rgba(0,0,0,0.51) 67%,rgba(0,0,0,1) 100%);
filter: progid:DXImageTransform.Microsoft.gradient( startColorstr='#00ffffff', endColorstr='#000000',GradientType=1 );


}

.hero {
  max-width: $layout_width;
  height: 500px;
  position: relative;
  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
  .transparent {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    @include gradient_light;

    @media (prefers-color-scheme: dark) {
      @include gradient_dark;
    }
  }
}
</style>