<template>
<modal-window @click-btn="submit">
  <template #title>
    <h1>Оставьте Ваш номер телефона <br> И&nbsp;мы&nbsp;свяжемся с&nbsp;Вами</h1>
  </template>
  <template #body>
    <UiInput
      v-model:value="v$.name.$model"
      :errors="v$.name.$errors"
      placeholder="Имя"
    />
    <UiInput
      v-model:value="v$.phone.$model"
      :errors="v$.phone.$errors"
      type="tel" 
      placeholder="Номер телефона"
    />
    <UiInput
      v-model:value="v$.time.$model"
      :errors="v$.time.$errors"
      placeholder="Удобное время для звонка"
    />
  </template>
  <template #textBtn>
    <span>Заказать звонок</span> 
  </template>
</modal-window>
</template>

<script>
import UiInput from '../UI/UiInput.vue';
import ModalWindow from './ModalWindow';
import { useVuelidate } from '@vuelidate/core'
import { helpers, required  } from '@vuelidate/validators'

export default {
  name: 'CallbackModal',
  components: {
    ModalWindow,
    UiInput
  },
  setup () {
    return { v$: useVuelidate() }
  },
  data: () => ({
    name: '',
    phone: '',
    time: '',
    validationsRequired: helpers.withMessage('Обязательно для заполнения', required),
  }),
  validations() {
    return {
      name: { required: this.validationsRequired },
      phone: { required: this.validationsRequired },
      time: { required: this.validationsRequired }
    }
  },
  methods: {
    async submit() {
      const isFormCorrect = await this.v$.$validate()
      if (!isFormCorrect) return

      this.close()
    },
    close() {
      this.$emit('close')
    }
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
</style>