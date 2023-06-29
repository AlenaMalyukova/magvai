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
    <p>Заказать звонок</p>   
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
.input {
  width: 450px;
  margin-bottom: 20px;
  padding: 15px 20px;
  font-size: 20px;
  border-radius: 5px;
  box-sizing: border-box;
  border: 1px solid gray;
  background: transparent;
  color: #fafafa;
}
</style>