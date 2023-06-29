<template>
  <div class="actions">
    <button class="btn phone-btn" @click="toggleCallbackModal">
      <span class="icon-phone phone-btn__icon"></span>
    </button>
    <button class="btn proposal-btn" @click="toggleProposalModal">
      <span>ОСТАВИТЬ ЗАЯВКУ</span>
    </button>
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
  position: relative;

  @include phones {
    display: none;
  }
}
.btn {
  display: flex;
  justify-content: center;
  align-items: center;
  cursor: pointer;
  transform: skew(-20deg);
}

.phone-btn {
  background-color: transparent;
  color: #1F2939;;
  padding: 18px 36px;
  border: 1px solid #ffffff59;
  margin-right: 25px;
  box-sizing: border-box;

  &:hover {
    border-color: #C2AB81;
    
    span{
      color: #C2AB81;
      transition: .3s;
    }
  }

  &__icon{
    width: 20px;
    height: 20px;
    transform: skew(20deg);
    font-size: 20px;
    color: gray;
  }
}

.proposal-btn {
  background: #C2AB81;
  padding: 21px 0;
  width: 282px;
  color: #fff;
  border: none;
  font-size: 12px;
  font-weight: 700;
  line-height: 1.3;
  position: relative;

  @include tablets {
    width: 200px;
  }

  &:hover {
    background: #c4a162;
  }

  &::after {
    content: '';
    position: absolute;
    display: block;
    width: 5px;
    height: 100%;
    background: #fff;
    top: 0;
    right: -10px;
  }

  span {
    transform: skew(20deg);
  }
}
</style>