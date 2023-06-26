<template>
<div class="modal-shadow" @click.self="close">
  <div class="modal">
    <div class="modal-close" @click="close">&#10006;</div>
    <slot name="title">
      <h3 class="modal-title">Заголовок</h3>
    </slot>
    <slot name="body">
      <div class="modal-content">
        Дефолтный контент модального окна
      </div>
    </slot>
    <slot name="footer">
      <div class="modal-footer">
        <button class="modal-footer__button" @click="close">
          Ок
        </button>
      </div>
    </slot>
  </div>
</div>
</template>

<script>
export default{
  name: 'ModalWindow',
  methods: {
    close() {
      this.$emit('close')
      console.log('modal-window')
    }
  }
}
</script>

<style lang="scss" scoped>
.modal-shadow {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 10;
  min-height: 100%;
  width: 100%;
  background: rgba(0, 0, 0, 0.39);
}

.modal {
  background: #fff;
  border-radius: 8px;
  padding: 40px 30px 30px;
  min-width: 420px;
  max-width: 480px;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: column;
  align-items: center;

  &-close {
    border-radius: 50%;
    color: #fff;
    background: #2a4cc7;
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute;
    top: 25px;
    right: 25px;
    width: 30px;
    height: 30px;
    cursor: pointer;
  }

  &-title {
    color: #0971c7;
  }

  &-content {
    margin-bottom: 20px
  }

  &-footer {
    &__button {
      background-color: #0971c7;
      color: #fff;
      border: none;
      text-align: center;
      padding: 8px;
      font-size: 17px;
      font-weight: 500;
      border-radius: 8px;
      min-width: 150px;
    }
  }
}
</style>