<template>
  <NuxtLink :to="$i18n.path('')" class="header--logo" exact>Denis Goldman</NuxtLink>
</template>

<script>
export default {
  name: "Logo"
}
</script>

<style lang="scss">
  .header--logo {
    font-family: "Quicksand", serif;
    font-weight: 700;
    color: #000;
    text-decoration: none;

    @media (prefers-color-scheme: dark) {
      color: #fff;
    }

  }
</style>
