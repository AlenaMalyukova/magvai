<template>
  <div class="container">
    <div class="list">
      <h1 class="list__title">Карточки</h1>
      <Loader v-if="isLoading"/>
      <div v-else class="cards">
        <CardItem v-for="card in cards" :key="card.id" :card="card"/>
      </div>
      <button 
        class="list__btn"
        v-if="cards.length < 30"
        @click="loadMorePosts"
      >
        <span>ЗАГРУЗИТЬ ЕЩЕ</span>
      </button>
    </div>
  </div>
</template>

<script>
import CardItem from './CardItem.vue'
import Loader from './Loader.vue'
import axios from '../plugins/axios'

export default {
  name: 'CardList',
  components: {
    CardItem,
    Loader
  },
  data: () => ({
    isLoading: true,
    cards: [],
    page: 1,
  }),
  async mounted() {
    await this.loadPosts();
  },
  methods: {
    async loadPosts() {
      try {
        const { data } = await axios({
          method: 'GET',
          url: '/posts',
          params: {
            _page: this.page,
            _limit: 10,
          },
        });

        this.cards = [...this.cards, ...data];
      } catch(err) {
        console.log(err);
      } finally {
        this.isLoading = false;
      }
    },
    async loadMorePosts() {
      try {
        const { data } = await axios({
          method: 'GET',
          url: '/posts',
          params: {
            _page: this.page += 1,
            _limit: 5,
          },
        });

        this.cards = [...this.cards, ...data];
      } catch(err) {
        console.log(err);
      } finally {
        this.isLoading = false;
      }
    }
  }
}
</script>

<style lang="scss" scoped>
@import '@/styles/mixins.scss';

.container {
  max-width: 1720px;
  padding: 0 100px;
  margin: 0 auto;

  @include tablets {
    // max-width: 665px;
    padding: 0 50px;
  }

  @include phones {
    padding: 0 15px;
  }
}

.list {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding-bottom: 256px;

  @include tablets {
    padding-bottom: 156px;
  }

  @include phones {
    padding-bottom: 43px;
  }

  &__title {
    font-size: 42px;
    font-weight: 700;
    line-height: 1.2;
    text-transform: uppercase;
    align-self: flex-start;
    padding-top: 134px;

    @include tablets {
      padding-top: 44px;
    }

    @include phones {
      padding-top: 30px;
      font-size: 20px;
    }
  }

  &__btn {
    background: #C2AB81;
    padding: 21px 85px;
    color: #fff;
    border: none;
    font-size: 12px;
    font-weight: 700;
    cursor: pointer;
    transform: skew(-20deg);

    &:hover {
      background: #c4a162;
    }

    span {
      transform: skew(20deg);
    }
  }
}

.cards {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-gap: 30px;
  padding-top: 25px;
  padding-bottom: 50px;

  @include tablets {
    padding-top: 0;
    grid-template-columns: repeat(3, 1fr);
    grid-gap: 20px;
  }

  @include phones {
    padding-bottom: 30px;
    grid-template-columns: repeat(1, 1fr);
  }
}
</style>