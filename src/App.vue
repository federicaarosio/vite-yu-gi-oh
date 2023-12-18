<template lang="">
  <main>
    <AppHeader />
    <CardsList :cardsList="cards" />
  </main>
</template>
<script>
import axios from 'axios';
import AppHeader from './components/AppHeader.vue';
import CardsList from './components/CardsList.vue'

export default {
  name: 'AppaVue',
  components: {
    AppHeader,
    CardsList
  },
  data() {
    return {
      cards: [],
    }
  },
  methods: {
    getCards(){
      axios.get('https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0')
      .then((response) => {
        console.log(response.data.data);
        this.cards = response.data.data;
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
  
</style>