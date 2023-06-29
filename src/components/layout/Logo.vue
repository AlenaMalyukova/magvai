<template>
  <div class="logo">
    <img src="@/assets/images/logo.svg" alt="logo">
  </div>
</template>

<script>
export default {
  name: 'Logo'
}
</script>

<style lang="scss" scoped>
@import '@/styles/mixins.scss';

.logo {
  padding-right: 76px;

  @include tablets {
    padding-right: 0;
  }

  img {
    max-width: 156px;
    max-height: 60px;

    @include phones {
      width: 112px;
      height: 38px;
    }
  }
}
</style>