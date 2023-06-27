<template>
  <div class="actions">
    <button class="actions-phone" @click="toggleModal">
      <img src="@/assets/icons/phone.svg" alt="phone">
    </button>
    <button class="actions-application" @click="toggleSubmitModal">ОСТАВИТЬ ЗАЯВКУ</button>
  </div>
  <ApplicationModal v-if="isModalVisible" @close="toggleModal"/>
  <SubmitModal v-if="isSubmitModalVisible" @close="toggleSubmitModal"/>
</template>

<script>
import ApplicationModal from "../modal/ApplicationModal.vue";
import SubmitModal from "../modal/SubmitModal.vue";

export default {
  name: 'Actions',
  components: {
    ApplicationModal,
    SubmitModal
  },
  data: () => ({
    isModalVisible: false,
    isSubmitModalVisible: false
  }),
  methods: {
    toggleModal() {
      this.isModalVisible = !this.isModalVisible
    },
    toggleSubmitModal() {
      this.isSubmitModalVisible = !this.isSubmitModalVisible
    }
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
    cursor: pointer;

    img{
      fill: #ffffff;
      width: 20px;
      height: 20px;
    }
  }

  &-application {
    background: #C2AB81;
    padding: 21px 0;
    width: 282px;
    color: #fff;
    border: none;
    font-size: 18px;
    font-weight: 700;
    cursor: pointer;
  }
}
</style>