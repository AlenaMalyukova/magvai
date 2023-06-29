<template>
  <div class="card">
    <img class="card__img" :src="require('../assets/images/money.png')" alt="image">
    <div class="text">
      <h4 class="text__title">{{ card.title }}</h4>
      <h5 class="text__description">{{ card.body }}</h5>
      <button class="text__btn">Continue reading</button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CardItem',
  props: { 
    card: Object
  }
}
</script>

<style lang="scss" scoped>
@import '@/styles/mixins.scss';

.card {
  display: flex;
  flex-direction: column;
  flex-shrink: 1;

  &__img {
    width: 100%;
    max-height: 185px;
    object-fit: cover;
  }
}

.text {
  color: #171717;
  padding: 10px 23px 30px;
  background: #fff;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  height: 100%;

  &__title {
    font-weight: 400;
  }

  &__description {
    margin-top: 0;
    font-weight: 400;
  }

  &__btn {
    padding: 16px;
    background: #171717;
    color: #fff;
    border: none;
    font-size: 14px;
    font-weight: 600;
    line-height: 1.2;
    align-self: center;
    width: 100%;
    cursor: pointer;

    &:hover {
      background: #000;
    }
  }
}
</style>