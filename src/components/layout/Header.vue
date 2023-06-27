<template>
  <div class="header">
    <div class="nav-wrapper">
      <Logo/>
      <Navigations/>
    </div>
    <Actions/>
  </div>
</template>

<script>
import Navigations from './Navigations.vue'
import Logo from './Logo.vue';
import Actions from './Actions.vue'

export default{
name: 'Header',
components: {
  Navigations,
  Logo,
  Actions
}
}
</script>

<style lang="scss" scoped>
.header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 30px 100px;
}

.nav-wrapper {
  display: flex;
  justify-content: flex-start;
  align-items: center;
}
</style>