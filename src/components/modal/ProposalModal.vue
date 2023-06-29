<template>
  <modal-window>
    <template #title>
      <h1>Оставить заявку</h1>
    </template>
    <template #body>
      <input class="input" type="text" name="firstName" placeholder="Имя">
      <input class="input" type="tel" name="tel" placeholder="Номер телефона">
      <input class="input" type="email" name="email" placeholder="E-mail">
      <textarea
        class="input textarea" 
        name="message"
        id="message"
        placeholder="Описание"
        rows="4"
      ></textarea>
    </template>
    <template #textBtn>
      <span>Отправить</span>
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
    max-width: 400px;
  }

  @include phones {
    font-size: 14px;
    margin-bottom: 10px;
    padding: 10px 10px;
    max-width: 380px;
  }
}
</style>