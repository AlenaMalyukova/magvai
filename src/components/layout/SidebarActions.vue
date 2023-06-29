<template>
  <div class="sidebar-actions">
    <button class="phone" @click="toggleCallbackModal">
      <img src="@/assets/icons/phone.svg" alt="phone">
    </button>
    <button class="sidebar-actions__proposal" @click="toggleProposalModal">ОСТАВИТЬ ЗАЯВКУ</button>
  </div>
</template>

<script>
export default {
  name: 'SidebarActions',
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

.sidebar-actions {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-top: 50px;

  @include tablets {
    display: none;
  }

  @include phones {
    display: flex;
  }

  &__proposal {
    background: #C2AB81;
    padding: 21px 0;
    width: 100%;
    color: #fff;
    border: none;
    font-size: 12px;
    font-weight: 700;
    line-height: 1.3;
    cursor: pointer;

    &:hover {
      background: #c4a162;
    }
  }
}

.phone {
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: transparent;
  color: #1F2939;;
  padding: 18px 36px;
  border: 1px solid #ffffff59;
  cursor: pointer;
  box-sizing: border-box;
  width: 100%;
  margin-bottom: 5px;

  &:hover {
    border-color: #C2AB81;
  }

  img{
    width: 20px;
    height: 20px;
  }
}
</style>

