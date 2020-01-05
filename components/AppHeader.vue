<template>
<div class="header-container">
  <header class="header">
    <input class="hidden-checkbox" type="checkbox" id="header-checkbox" />
    <div class="header--nav-strip">
      <label class="header--checkbox-label" for="header-checkbox">
        <BurgerIcon />
      </label>
      <div class="header--logo">
        <Logo />
      </div>
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
  </div>
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

.header {
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 100;
  @include header_light;

  @media (prefers-color-scheme: dark) {
    @include header_dark;
  }

  .header--link {
    font-size: 17px;
    font-family: "Quicksand", sans-serif;
    font-weight: 500;
    text-decoration: none;
    transition: all 0.3s;

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
      transition: all 0.3s;
      @include gradient_sunset;
      -webkit-text-fill-color: transparent;
      box-decoration-break: clone;
      background-clip: text;
    }
  }

  .header--nav-strip {
    display: flex;
    justify-content: space-between;
    height: 50px;
    padding: 0 20px;
    align-items: center;

    .language-selector__mobile {
      .header--link {
        font-size: 14px;
      }
    }
  }

  .header--menu {
    box-shadow: 0 4px 12px 0 rgba(0,0,0,.05);
    @media (prefers-color-scheme: dark) {
      border-bottom: 1px solid #333;
      box-shadow: none;
    }

    .header--menu__links {
      .header--link {
        padding: 10px 0;
      }
      .header--link:last-of-type {
        padding-bottom: 0px;
      }
    }

    .header--menu__options {
      display: none;
    }
  }

  .hidden-checkbox {
    display: none;
    & ~ nav {
      max-height: 0;
      overflow: hidden;
      opacity: 0;
      padding: 0 20px 0 20px;
      transition: max-height 0.8s cubic-bezier(0, 1, 0, 1), opacity 0.5s ease-in,
        padding 0.8s ease-in;
    }

    &:checked ~ nav {
      max-height: 100vh;
      overflow: visible;
      opacity: 1;
      padding: 0 20px 20px 20px;
      transition: max-height 0.8s ease-in, opacity 0.3s ease-in,
        padding 0.1s ease-in;
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

@media (min-width: $breakpoint_mobile) {

  .header-container {
    position: fixed;
    top: 0;
    width: 100%;
    @include header_light;
    @media (prefers-color-scheme: dark) {
      @include header_dark;
    }
  }

  .header {
    display: flex;
    max-width: $layout_width;
    position: relative;
    margin: 0 auto;
    box-shadow: none;
    background: none;
    .header--nav-strip {
      padding: 0 20px;
      .header--checkbox-label {
        display: none;
      }
      .language-selector__mobile {
        display: none;
      }
    }

    .header--menu {
      display: flex;
      align-items: center;
      flex-grow: 1;
      justify-content: space-between;
      box-shadow: none;
      .header--menu__links {
        flex-direction: row;
        .header--link:not(:first-of-type) {
          margin-left: 20px;
        }
        .header--link {
          transition: all 0.5s;
          font-size: 15px;
          &:hover {
            cursor: pointer;
            transition: all 0.5s;
            @include gradient_sunset;
            -webkit-text-fill-color: transparent;
            box-decoration-break: clone;
            background-clip: text;
          }
        }
      }
      .header--menu__options {
        display: block;
        .header--link {
          font-size: 15px;
        }
      }
    }

    .hidden-checkbox ~ nav {
      opacity: 1;
      max-height: 100vh;
      border-bottom: none;
      padding: 0;
      padding-right: 20px;
      transition: none;
    }
  }
}

@media (min-width: $layout_width) {
  .header {
  .header--nav-strip {
    padding-left: 0;
  }
  .hidden-checkbox ~ nav {
    padding-right: 0;
  }
  }
}


</style>