<template lang="">
  <main>
    <AppHeader />
    <AppSelect />
    <CardsList :cardsList="cards" />
  </main>
</template>
<script>
import {store} from './js/store.js';
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import AppSelect from './components/AppSelect.vue';
import CardsList from './components/CardsList.vue'

export default {
  name: 'AppaVue',
  components: {
    AppHeader,
    AppSelect,
    CardsList
  },
  data() {
    return {
      cards: [],
      store
    }
  },
  methods: {
    getCards(){
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then((response) => {
        console.log(response.data.data);
        this.store.cardsList = response.data.data;
      })
      .catch(function (error) {
        console.log(error);
      });

    }
  },
  created() {
    this.getCards();
  }
}
</script>
<style lang="scss">
@use './styles/general.scss';
@use './styles/partials/variables' as *;

  main {
    background-color: $bg-color;
  }
  
</style>