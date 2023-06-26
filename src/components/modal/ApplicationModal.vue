<template>
<modal-window>
  <template #title>
    <h2>Оставьте Ваш номер телефона <br> И мы свяжемся с Вами</h2>
  </template>
  <template #body>
    <input type="tel" name="tel" class="input number" placeholder="phone number">
    <input type="text" name="message" class="input time" placeholder="convenient time to call">
  </template>
  <template #footer>
    <button class="modal-footer__button" @click="close">
      Request a call
    </button>
  </template>
</modal-window>
</template>

<script>
import ModalWindow from './ModalWindow';

export default{
  name: 'ApplicationModal',
  components: {
    ModalWindow,
  },
  methods: {
    close(){ 
      this.$emit('close')
      console.log('application')
    } 
  }
}
</script>

<style lang="scss" scoped>
.input {
  width: 300px;
  margin-bottom: 10px;
  padding: 8px 15px;
  font-size: 14px;
  border-radius: 5px;
  box-sizing: border-box;
  border: 1px solid #818181;

  // &:focus,
  // &:active {
  //   border-color: #5243C2;
  // }
}

.modal-footer__button {
  background-color: #5243C2;
  padding: 8px 15px;
  margin-top: 10px;
  color: #fff;
  border: none;
  border-radius: 5px;

  &:hover {
    background-color: #413599;
  }
}

::v-deep{
  .modal{
    background: #131313;

    // &-close{
    //   background: transparent;
    // }
  }
}
</style>