<template>
  <div class="sidebar">
    <div class="container">
      <div class="nav">
        <a href="#" class="nav__link" v-for="link in links" :key="link.text"> {{ link.text }}</a>
      </div>
      <div class="actions">
        <SidebarActions 
          @toggle-callback="toggleCallbackModal"
          @toggle-proposal="toggleProposalModal"
        />
      </div>
    </div>
  </div>
</template>

<script>
import SidebarActions from './SidebarActions.vue';

export default {
  name: 'Sidebar',
  components: {
    SidebarActions
  },
  props: {
    isSidebarOpen: {
      type: Boolean,
      default: false
    },
    links: Array,
  },
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

.container {
  padding: 0 100px;
  display: flex;
  flex-direction: column;
  height: 90%;

  @include tablets {
    padding: 0 50px;
  }

  @include phones {
    padding: 0 15px;
  }
}

.sidebar {
  position: fixed;
  z-index: 999;
  top: 123px;
  bottom: 0;
  width: 100%;
  height: 100%;
  background-color: #131313;

  @include phones {
    top: 81px;
  }
}

.nav {
  display: flex;
  flex-direction: column;
  align-items: flex-start;
  padding: 60px 0px;
  height: max-content;

  &__link {
    font-size: 36px;
    font-weight: 700;
    line-height: 1.5;
    color: #131313;
    text-shadow:  1px 0 1px gray, 
                  0 1px 1px gray, 
                  -1px 0 1px gray, 
                  0 -1px 1px gray;
    text-decoration: none;

    @include phones {
      font-size: 20px;
    }

    &:hover {
      text-shadow: 1px 0 1px #C2AB81, 
                  0 1px 1px #C2AB81, 
                  -1px 0 1px #C2AB81, 
                  0 -1px 1px #C2AB81;
    }
  }
}

.actions {
  margin-bottom: 30px;
  margin-top: auto;
}
</style>

