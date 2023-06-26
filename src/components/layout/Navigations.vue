<template>
  <div class="nav">
    <a href="#" class="nav__link" v-for="link in links" :key="link.text"> {{ link.text }}</a>
  </div>
</template>
  
<script>
export default {
  name: 'Navigations',
  data: () => ({
    links: [
      { text: 'АБОНЕМЕНТЫ' },
      { text: 'ПОЧЕМУ' },
      { text: 'МЫ' },
      { text: 'ОБОРУДОВАНИЕ' },
      { text: 'АКЦИИ' },
      { text: 'FAQ' },
      { text: 'КОНТАКТЫ' },
    ]
  })
}
</script>

<style lang="scss" scoped>
.nav {
  display: flex;
  align-items: center;

  &__link{
    color: #fff;
    font-size: 14px;
    font-weight: 700;
    line-height: 1.2;
    text-decoration: none;
    margin-right: 42px;

    &:last-child {
      margin-right: 0;
    }

    &:hover,
    &:focus{
      color: gray;
    }
  }
}
</style>