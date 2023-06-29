<template>
<modal-window>
  <template #title>
    <h1>Оставьте Ваш номер телефона <br> И&nbsp;мы&nbsp;свяжемся с&nbsp;Вами</h1>
  </template>
  <template #body>
    <input type="tel" name="tel" class="input" placeholder="номер телефона">
    <input type="text" name="message" class="input" placeholder="удобное время для звонка">
  </template>
  <template #textBtn>
    <span>Заказать звонок</span>   
  </template>
</modal-window>
</template>

<script>
import ModalWindow from './ModalWindow';

export default {
  name: 'CallbackModal',
  components: {
    ModalWindow,
  },
}
</script>

<style lang="scss" scoped>
@import '@/styles/mixins.scss';

h1 {
  @include tablets {
    font-size: 24px;
    max-width: 400px;
  }

  @include phones {
    font-size: 16px;
    max-width: 320px;
  }
}

.input {
  max-width: 450px;
  width: 100%;
  margin-bottom: 20px;
  padding: 15px 20px;
  font-size: 20px;
  border-radius: 5px;
  box-sizing: border-box;
  border: 1px solid gray;
  background: transparent;
  color: #fafafa;

  @include tablets {
    font-size: 16px;
    margin-bottom: 15px;
    padding: 10px 15px;
    width: 90%;
  }

  @include phones {
    font-size: 14px;
    margin-bottom: 10px;
    padding: 10px 10px;
    max-width: 380px;
  }
}
</style>