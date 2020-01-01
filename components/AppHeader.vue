<template>
  <header class="header">
        <nav class="header--menu">
            <div class="header--menu__left">
                <NuxtLink :to="$i18n.path('')" class="header--link" exact>
                    {{ $t('links.home') }}
                </NuxtLink>
                <NuxtLink :to="$i18n.path('about')" class="header--link" exact>
                    {{ $t('links.about') }}
                </NuxtLink>
            </div>
            <div class="header--menu__right">
                <NuxtLink v-if="$i18n.locale === 'de'" :to="`/en` + $route.fullPath" class="header--link" active-class="none" exact>
                    {{ $t('links.english') }}
                </NuxtLink>
                <NuxtLink v-else :to="$route.fullPath.replace(/^\/[^\/]+/, '')" class="header--link" active-class="none" exact>
                    {{ $t('links.german') }}
                </NuxtLink>
            </div>
          
          
        </nav>
    </header>
</template>

<script>
export default {
    name: "AppHeader"
}
</script>

<style lang="scss">
    .header {
        height: $header_height;
        line-height: $header_height;
        position: fixed;
        width: 100%;
        @include header_light;

        .header--menu {
            max-width: $layout_width;
            margin: 0 auto;
            display: flex;
            justify-content: space-between;
            padding: 0 20px;
        }

        .header--link {
            font-size: 14px;
            font-family: "Quicksand", sans-serif;
            text-decoration: none;
            transition: color .3s;

            &:visited {
                color: #000;
            }

            &:hover {
                color: blue;
                transition: color .3s;
            }
        }

        @media (prefers-color-scheme: dark) {
            @include header_dark;
        }

    }
</style>