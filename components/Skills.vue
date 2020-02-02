<template>
  <div class="skills">
    <div class="skills__header">
      <h2 class="skills__title">{{$t('skills.title')}}</h2>
      <h4 class="skills__subtitle">{{$t('skills.subtitle')}}</h4>
    </div>
    <ul class="skills__row">
      <li class="skills__item">
        <img class="icon" :src="require(`@/assets/icons/web-programming.svg`)" />
        <h4 class="title">{{$t('skills.webdev')}}</h4>
      </li>
      <li class="skills__item">
          <i class="icon fab fa-react"></i>
        <h4 class="title">{{$t('skills.react')}}</h4>
      </li>
      <li class="skills__item">
          <i class="icon fab fa-js"></i>
        <h4 class="title">{{$t('skills.javascript')}}</h4>
      </li>
      <li class="skills__item">
          <i class="icon fab fa-vuejs"></i>
        <h4 class="title">{{$t('skills.vue')}}</h4>
      </li>
      <li class="skills__item">
          <i class="icon fab fa-sass"></i>
        <h4 class="title">{{$t('skills.sass')}}</h4>
      </li>
      <li class="skills__item">
          <img class="icon" :src="require(`@/assets/icons/idea.svg`)" />
        <h4 class="title">{{$t('skills.design')}}</h4>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Skills"
};
</script>

<style lang="scss">
.skills {
  margin-top: 10px;
  margin-bottom: 10px;
  background: $areaColor_light;
  @media (prefers-color-scheme: dark) {
    background: $areaColor_dark;
  }

  &__header {
    text-align: center;
    padding: 20px;
  }

  &__subtitle {
      @media (prefers-color-scheme: dark) {
          color: $secondaryTextColor;
      }
  }

    &__row {
        margin: 0;
        padding: 0 0 20px 0;
        display: grid;
        grid-row-gap: 30px;
        list-style-type: none;
        grid-template-columns: repeat(auto-fit, minmax(200px , 1fr));
        @media (min-width: $breakpoint_mobile) {
            padding: 40px 20px 60px 20px;
        }
    }

    &__item {
        display: flex;
        flex-direction: column;
        text-align: center;

        .icon {
            margin-bottom: 10px;
        }

        i {
            font-size: 4em;
            @media (prefers-color-scheme: dark) {
                color: #fff;
            }
            @media (min-width: $breakpoint_mobile) {
            font-size: 5em;
        }
        }

        img {
            max-height: 55px;
            padding: 5px;
            @media (prefers-color-scheme: dark) {
                filter: invert(100%);
            }
            @media (min-width: $breakpoint_mobile) {
            max-height: 65px;
        }
            
        }

        //<div>Icons made by <a href="https://www.flaticon.com/authors/icongeek26" title="Icongeek26">Icongeek26</a> from <a href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a></div>
        //<div>Icons made by <a href="https://www.flaticon.com/authors/smashicons" title="Smashicons">Smashicons</a> from <a href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a></div>

    }

}
</style>