<template>
  <div class="Content">
    <div class="container">
      <div class="Content__Title">
        {{ $t('home.title') }}
      </div>
      <p>{{ $t('home.introduction') }}</p>
    </div>
  </div>
</template>

<script>
export default {
  head () {
    return { title: this.$t('home.title') }
  }
}
</script>
