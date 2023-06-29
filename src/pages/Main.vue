<template>
  <Intro />
  <CardList/>
</template>

<script>
import Intro from '../components/Intro.vue';
import CardList from '../components/CardList.vue';

export default {
  name: 'Main',
  components: {
    Intro,
    CardList
  }
}
</script>