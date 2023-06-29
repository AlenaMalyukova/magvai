<template>
  <div :class="headerClass">
    <button class="sidebar-btn" @click="toggleSidebar">
      <img src="@/assets/icons/sidebar.svg" alt="sidebar">
    </button>
    <div class="nav-wrapper">
      <Logo/>
      <Navigations :links="links"/>
    </div>
    <Actions
      @toggle-callback="toggleCallbackModal"
      @toggle-proposal="toggleProposalModal"
    />
  </div>
  <Sidebar v-if="isSidebarOpen" :links="links" @close="toggleSidebar" @toggle-callback="toggleCallbackModal"
      @toggle-proposal="toggleProposalModal"/>
  <CallbackModal 
    v-if="isCallbackModalVisible" 
    @close="toggleCallbackModal"
  />
  <ProposalModal 
    v-if="isProposalModalVisible" 
    @close="toggleProposalModal" 
  />
</template>

<script>
import Navigations from './Navigations.vue'
import Logo from './Logo.vue';
import Actions from './Actions.vue'
import Sidebar from './Sidebar.vue';
import CallbackModal from "../modal/CallbackModal.vue";
import ProposalModal from "../modal/ProposalModal.vue";

export default{
  name: 'Header',
  components: {
    Navigations,
    Logo,
    Actions,
    Sidebar,
    CallbackModal,
    ProposalModal
  },
  data: () => ({
    isSidebarOpen: false,
    isCallbackModalVisible: false,
    isProposalModalVisible: false,
    links: [
      { text: 'УСЛУГИ' },
      { text: 'АБОНЕМЕНТЫ' },
      { text: 'ПОЧЕМУ МЫ' },
      { text: 'ОБОРУДОВАНИЕ' },
      { text: 'АКЦИИ' },
      { text: 'FAQ' },
      { text: 'КОНТАКТЫ' },
    ]
  }),
  methods: {
    toggleSidebar() {
      this.isSidebarOpen = !this.isSidebarOpen
    },
    toggleCallbackModal() {
      if(this.isSidebarOpen) {
        this.isSidebarOpen = false
      }

      this.isCallbackModalVisible = !this.isCallbackModalVisible
    },
    toggleProposalModal() {
      if(this.isSidebarOpen) {
        this.isSidebarOpen = false
      }

      this.isProposalModalVisible = !this.isProposalModalVisible
    }
  },
  computed: {
    headerClass() {
      return this.isSidebarOpen ? 'header header_fixed' : 'header'
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/styles/mixins.scss';

.header {
  box-sizing: border-box;
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 30px 100px;
  width: 100%;
  position: relative;

  @include tablets {
    padding: 30px 50px;
  }

  @include phones {
    padding: 20px 15px;
  }

  &_fixed {
    position: fixed;
    background: #131313;
    z-index: 999;
  }
}

.nav-wrapper {
  display: flex;
  justify-content: flex-start;
  align-items: center;
}

.sidebar-btn {
  display: none;
  background: transparent;
  border: none;
  cursor: pointer;

  @include tablets {
    display: flex;
  }
}
</style>