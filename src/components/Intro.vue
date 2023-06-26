<template>
  <div class="intro">
    <h1 class="intro__title">Полет Илона Маска <br/> и DOGIE COIN</h1>
    <h3 class="intro__desc">В прошлый четверг все офигели от полета DOGIE COIN на марс.</h3>
    <button class="intro__application">ОСТАВИТЬ ЗАЯВКУ</button>
  </div>
</template>

<script>
export default {
  name: 'Intro'
}
</script>

<style lang="scss" scoped>
.intro {
  background: url('../assets/images/bg-intro.png');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  height: 920px;
  border-radius: 48px 48px 0 0;
  position: relative;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-end;
  padding: 0 0 96px 100px;

  &::before {
    content: '';
    display: block;
    position: absolute;
    width: 100%;
    height: 520px;
    background: linear-gradient(to top, #131313, transparent);
    bottom: 0;
    left: 0;
  }

  &__title {
    font-size: 42px;
    font-weight: 700;
    line-height: 1.2;
    z-index: 2;
    text-align: left;
    text-transform: uppercase;
  }

  &__desc {
    font-size: 16px;
    font-weight: 400;
    line-height: 1.5;
    z-index: 2;
    padding-bottom: 24px;
  }

  &__application {
    background: #C2AB81;
    padding: 21px 78px;
    color: #fff;
    border: none;
    font-size: 18px;
    font-weight: 700;
    z-index: 2;
  }
}
</style>