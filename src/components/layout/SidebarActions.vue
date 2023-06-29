<template>
  <div class="actions">
    <button class="actions-phone" @click="toggleModal">
      <img src="@/assets/icons/phone.svg" alt="phone">
    </button>
    <button class="actions-submit" @click="toggleSubmitModal">ОСТАВИТЬ ЗАЯВКУ</button>
  </div>
  <CallbackModal v-if="isModalVisible" @close="toggleModal"/>
  <SubmitModal v-if="isSubmitModalVisible" @close="toggleSubmitModal"/>
</template>

