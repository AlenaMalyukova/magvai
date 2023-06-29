<template>
  <div class="intro">
    <h1 class="intro__title">Полет Илона Маска <br/> и DOGIE COIN</h1>
    <h3 class="intro__desc">В прошлый четверг все офигели от полета DOGIE COIN на марс.</h3>
    <button class="intro__btn" @click="toggleProposalModal">
      <span>ОСТАВИТЬ ЗАЯВКУ</span>
    </button>
  </div>
  <ProposalModal v-if="isProposalModalVisible" @close="toggleProposalModal"/>
</template>

<script>
import ProposalModal from './modal/ProposalModal.vue';

export default {
  name: 'Intro',
  components: {
    ProposalModal
  },
  data: () => ({
    isProposalModalVisible: false
  }),
  methods: {
    toggleProposalModal() {
      this.isProposalModalVisible = !this.isProposalModalVisible
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/styles/mixins.scss';

.intro {
  background: url('../assets/images/bg-intro.png');
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
  border-radius: 48px 48px 0 0;
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  justify-content: flex-end;
  text-align: left;
  padding: 600px 100px 96px;

  @include tablets {
    padding: 551px 50px 76px;
    border-radius: 36px 36px 0 0;
  }

  @include phones {
    padding: 266px 15px 50px;
    border-radius: 24px 24px 0 0;
  }

  &::before {
    content: '';
    display: block;
    position: absolute;
    width: 100%;
    height: 520px;
    background: linear-gradient(to top, #131313, transparent);
    bottom: 0;
    left: 0;

    @include tablets {
      height: 480px;
    }

    @include phones {
      height: 281px;
    }
  }

  &__title {
    font-size: 42px;
    font-weight: 700;
    line-height: 1.2;
    z-index: 2;
    text-transform: uppercase;

    @include tablets {
      font-size: 38px;
    }

    @include phones {
      font-size: 20px;
      margin-bottom: 20px;
    }
  }

  &__desc {
    font-size: 16px;
    font-weight: 400;
    line-height: 1.5;
    z-index: 2;
    padding-bottom: 24px;
    color: #adadad;

    @include tablets {
      max-width: 450px;
    }

    @include phones {
      max-width: 300px;
      font-size: 14px;
      margin-top: 0;
      padding-bottom: 6px;
    }
  }

  &__btn {
    background: #C2AB81;
    padding: 21px 78px;
    color: #fff;
    border: none;
    font-size: 18px;
    font-weight: 700;
    z-index: 2;
    cursor: pointer;
    transform: skew(-20deg);
    position: relative;
    margin-left: 15px;

    @include phones {
      padding: 14px 46px;
      font-size: 12px;
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
}
</style>