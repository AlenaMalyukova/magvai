<template>
  <modal-window @click-btn="submit">
    <template #title>
      <h1>Оставить заявку</h1>
    </template>
    <template #body>
      <UiInput 
        v-model:value="v$.fullName.$model"
        :errors="v$.fullName.$errors"
        placeholder="Фамилия Имя Отчество"
      />
      <UiInput 
        v-model:value="v$.phone.$model"
        :errors="v$.phone.$errors"
        type="tel"
        placeholder="Номер телефона"
      />
      <UiInput 
        v-model:value="v$.email.$model"
        :errors="v$.email.$errors"
        placeholder="E-mail"
      />
      <UiTextarea 
        v-model:value="v$.desc.$model"
        :errors="v$.desc.$errors"
        placeholder="Описание" 
        rows="4"
      />
    </template>
    <template #textBtn>
      <span>Отправить</span>
    </template>
  </modal-window>
</template>
  
<script>
import ModalWindow from './ModalWindow.vue';
import UiInput from '../UI/UiInput.vue'
import UiTextarea from '../UI/UiTextArea.vue'
import { useVuelidate } from '@vuelidate/core'
import { helpers, required  } from '@vuelidate/validators'

export default {
  name: 'ProposalModal',
  components: {
    ModalWindow,
    UiInput,
    UiTextarea
  },
  setup () {
    return { v$: useVuelidate() }
  },
  data: () => ({
    fullName: '',
    phone: '',
    email: '',
    desc: '',
    validationsRequired: helpers.withMessage('Обязательно для заполнения', required),
  }),
  validations() {
    return {
      fullName: { required: this.validationsRequired },
      phone: { required: this.validationsRequired },
      email: { required: this.validationsRequired },
      desc: { required: this.validationsRequired },
    }
  },
  methods: {
    async submit() {
      const isFormCorrect = await this.v$.$validate()
      if (!isFormCorrect) return

      this.close()
    },
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
</style>