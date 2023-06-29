<template>
  <div class="actions">
    <button class="actions-phone" @click="toggleCallbackModal">
      <img src="@/assets/icons/phone.svg" alt="phone">
    </button>
    <button class="actions-proposal" @click="toggleProposalModal">ОСТАВИТЬ ЗАЯВКУ</button>
  </div>
</template>

<script>

export default {
  name: 'Actions',
  methods: {
    toggleCallbackModal() {
      this.$emit('toggle-callback')
    },
    toggleProposalModal() {
      this.$emit('toggle-proposal')
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/styles/mixins.scss';

.actions {
  display: flex;
  justify-content: flex-start;
  align-items: center;

  @include phones {
    display: none;
  }

  &-phone {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: transparent;
    color: #1F2939;;
    padding: 18px 36px;
    border: 1px solid #ffffff59;
    margin-right: 12.5px;
    cursor: pointer;
    box-sizing: border-box;

    img{
      width: 20px;
      height: 20px;
    }
  }

  &-proposal {
    background: #C2AB81;
    padding: 21px 0;
    width: 282px;
    color: #fff;
    border: none;
    font-size: 12px;
    font-weight: 700;
    line-height: 1.3;
    cursor: pointer;

    @include tablets {
      width: 200px;
    }
  }
}
</style>