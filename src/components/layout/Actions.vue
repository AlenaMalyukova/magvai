<template>
  <div class="actions">
    <pre> {{ isModalVisible }} </pre>
    <button class="actions-phone" @click="toggleModal">
      <img src="@/assets/icons/phone.svg" alt="phone">
    </button>
    <button class="actions-application">ОСТАВИТЬ ЗАЯВКУ</button>
  </div>
  <ApplicationModal v-if="isModalVisible" @close="toggleModal"/>
</template>

<script>
import ApplicationModal from "../modal/ApplicationModal.vue";

export default {
  name: 'Actions',
  components: {
    ApplicationModal
  },
  data: () => ({
    isModalVisible: false
  }),
  methods: {
    toggleModal() {
      this.isModalVisible = !this.isModalVisible
    },
  }
}
</script>

<style lang="scss" scoped>
.actions {
  display: flex;
  justify-content: flex-start;
  align-items: center;
  &-phone {
    display: flex;
    justify-content: center;
    align-items: center;
    background-color: transparent;
    color: #1F2939;;
    padding: 18px 36px;
    border: 1px solid #ffffff59;
    margin-right: 12.5px;

    img{
      fill: #ffffff;
      width: 20px;
      height: 20px;
    }
  }

  &-application {
    background: #C2AB81;
    padding: 21px 78px;
    color: #fff;
    border: none;
    font-size: 18px;
    font-weight: 700;
  }
}

// .callback {
//   color: #FF4D4F;
//   margin-right: 60px;
//   background: #FFEDED;

//   img{
//     max-width: 12px;
//     max-height: 12px;
//   }
// }
</style>