<template>
  <div class="sidebar-actions">
    <button class="btn phone-btn" @click="toggleCallbackModal">
      <img src="@/assets/icons/phone.svg" alt="phone">
    </button>
    <button class="btn proposal-btn" @click="toggleProposalModal">ОСТАВИТЬ ЗАЯВКУ</button>
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
  }
}

.btn {
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  transform: skew(-20deg);
  width: 95%;
  max-width: 400px;
}

.phone-btn {
  background-color: transparent;
  color: #1F2939;;
  padding: 18px 36px;
  border: 1px solid #ffffff59;
  box-sizing: border-box;
  margin-bottom: 6px;

  &:hover {
    border-color: #C2AB81;
  }

  img{
    width: 20px;
    height: 20px;
    transform: skew(20deg);
  }
}

.proposal-btn {
  background: #C2AB81;
  padding: 21px 0;
  color: #fff;
  border: none;
  font-size: 12px;
  font-weight: 700;
  line-height: 1.3;

  &:hover {
    background: #c4a162;
  }

  span {
    transform: skew(20deg);
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

