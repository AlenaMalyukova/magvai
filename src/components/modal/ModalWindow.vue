<template>
<div class="modal-shadow" @click.self="close">
  <div class="modal">
    <div class="modal-close" @click="close">&#10006;</div>
    <slot name="title">
      <h1 class="modal-title">Заголовок</h1>
    </slot>
    <slot name="body">
      <div class="modal-content">
        Дефолтный контент модального окна
      </div>
    </slot>
    <slot name="footer">
      <div class="modal-footer">
        <button class="modal-footer__button" @click="sendData">
          <slot name="textBtn">Ок</slot>
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
    },
    sendData() {
      this.$emit('click-btn')
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/styles/mixins.scss';

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
  background: #131313;
  border-radius: 8px;
  padding: 50px 40px 40px;
  max-width: 600px;
  width: 100%;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  display: flex;
  flex-direction: column;
  align-items: center;

  @include tablets {
    padding: 40px 30px 30px;
    max-width: 550px;
  }

  @include phones {
    padding: 30px 20px 20px;
    max-width: 400px;
    width: 250px;
  }

  &-close {
    border-radius: 50%;
    color: #fff;
    background: transparent;
    display: flex;
    align-items: center;
    justify-content: center;
    position: absolute;
    top: 25px;
    right: 25px;
    width: 30px;
    height: 30px;
    font-size: 24px;
    cursor: pointer;

    @include phones {
      top: 15px;
      right: 15px;
      font-size: 20px;
    }
  }

  &-title {
    color: #fff;
    font-size: 48px;
  }

  &-content {
    margin-bottom: 20px
  }

  &-footer {
    &__button {
      background: #C2AB81;
      color: #fff;
      border: none;
      text-align: center;
      padding: 20px;
      font-size: 20px;
      font-weight: 500;
      border-radius: 8px;
      min-width: 150px;
      margin-top: 20px;
      cursor: pointer;

      &:hover {
        background: #c4a162;
      }

      @include tablets {
        padding: 15px 20px;
        margin-top: 15px;
        font-size: 16px;
      }

      @include phones {
        padding: 10px 15px;
        margin-top: 10px;
        font-size: 14px;
      }
    }
  }
}
</style>