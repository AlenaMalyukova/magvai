<template>
  <modal-window>
    <template #title>
      <h1>Оставить заявку</h1>
    </template>
    <template #body>
      <input type="text" name="firstName" class="input" placeholder="Имя" required>
      <input type="tel" name="tel" class="input" placeholder="номер телефона" required>
      <input type="email" name="email" class="input" placeholder="E-mail" required>
      <textarea name="message" id="message" class=" input textarea" placeholder="Описание" required></textarea>
    </template>
    <template #textBtn>
      <p>Отправить</p>
    </template>
  </modal-window>
</template>
  
<script>
import ModalWindow from './ModalWindow.vue';

export default {
  name: 'ProposalModal',
  components: {
    ModalWindow,
  },
  methods: {
    close(){ 
      this.$emit('close')
    } 
  }
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

.textarea {
  width: 450px;
  height: 250px;
}
</style>