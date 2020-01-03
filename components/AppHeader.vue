<template>
  <header class="header">
    <input class="hidden-checkbox" type="checkbox" id="header-checkbox" />
    <div class="header--nav-strip">
    <label class="header--checkbox-label" for="header-checkbox"><BurgerIcon /></label>
    <div class="header--logo"><Logo /></div>
    <div class="language-selector__mobile">
        <NuxtLink
          v-if="$i18n.locale === 'de'"
          :to="`/en` + $route.fullPath"
          class="header--link"
          active-class="none"
          exact
        >{{ $t('links.englishCode') }}</NuxtLink>
        <NuxtLink
          v-else
          :to="$route.fullPath.replace(/^\/[^\/]+/, '')"
          class="header--link"
          active-class="none"
          exact
        >{{ $t('links.germanCode') }}</NuxtLink>
      </div>
    </div>
    <nav class="header--menu">
      <div class="header--menu__links">
        <NuxtLink :to="$i18n.path('')" class="header--link" exact>{{ $t('links.portfolio') }}</NuxtLink>
        <NuxtLink :to="$i18n.path('about')" class="header--link" exact>{{ $t('links.resume') }}</NuxtLink>
        <NuxtLink :to="$i18n.path('about')" class="header--link" exact>{{ $t('links.about') }}</NuxtLink>
      </div>
      <div class="header--menu__options">
        <NuxtLink
          v-if="$i18n.locale === 'de'"
          :to="`/en` + $route.fullPath"
          class="header--link"
          active-class="none"
          exact
        >{{ $t('links.english') }}</NuxtLink>
        <NuxtLink
          v-else
          :to="$route.fullPath.replace(/^\/[^\/]+/, '')"
          class="header--link"
          active-class="none"
          exact
        >{{ $t('links.german') }}</NuxtLink>
      </div>
    </nav>
  </header>
</template>

<script>
import Logo from "./Logo";
import BurgerIcon from "./BurgerIcon";
export default {
  name: "AppHeader",
  components: {
    Logo,
    BurgerIcon
  }
};
</script>

<style lang="scss">
// .header {
//     height: $header_height;
//     line-height: $header_height;
//     position: fixed;
//     width: 100%;
//     @include header_light;

//     .header--menu {
//         max-width: $layout_width;
//         margin: 0 auto;
//         display: flex;
//         justify-content: space-between;
//         padding: 0 20px;
//     }

//     .header--link {
//         font-size: 14px;
//         font-family: "Quicksand", sans-serif;
//         text-decoration: none;
//         transition: all .3s;

//         &:not(:first-of-type) {
//             margin-left: 20px;
//         }

//         @media (prefers-color-scheme: dark) {
//             color: $textColor_dark;
//         }

//         &:visited {
//             color: $textColor_light;

//             @media (prefers-color-scheme: dark) {
//             color: $textColor_dark;
//         }

//         }

//         &:hover {
//             transition: all .3s;
//             background: linear-gradient(90deg,#ff8a00,#e52e71);
//             -webkit-text-fill-color: transparent;
//             box-decoration-break: clone;
//             background-clip: text;
//         }
//     }

//     @media (prefers-color-scheme: dark) {
//         @include header_dark;
//     }

// }

.header {

  .header--link {
        font-size: 14px;
        font-family: "Quicksand", sans-serif;
        text-decoration: none;
        transition: all .3s;

        @media (prefers-color-scheme: dark) {
            color: $textColor_dark;
        }

        &:visited {
            color: $textColor_light;

            @media (prefers-color-scheme: dark) {
            color: $textColor_dark;
        }

        }

        &:hover {
            transition: all .3s;
            background: linear-gradient(90deg,#ff8a00,#e52e71);
            -webkit-text-fill-color: transparent;
            box-decoration-break: clone;
            background-clip: text;
        }
    }

  .header--nav-strip {
      display: flex;
      justify-content: space-between;
      height: 50px;
      align-items: center;

    .header--checkbox-label {
        height: 50px;
    }

  }

  .hidden-checkbox {
    display: none;
    & ~ nav {
      max-height: 0;
      overflow: hidden;
      opacity: 0;
      transition: max-height 0.8s cubic-bezier(0, 1, 0, 1), opacity 0.5s ease-in;
    }

    &:checked ~ nav {
      max-height: 100vh;
      overflow: visible;
      opacity: 1;
      transition: max-height 0.8s ease-in, opacity 0.3s ease-in;
    }
  }

  .header--menu {
    display: block;
  }

  .header--menu__links {
    display: flex;
    flex-direction: column;

    
  }
}
</style>