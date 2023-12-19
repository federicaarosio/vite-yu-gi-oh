<template lang="">
  <main>
    <AppHeader />
    <AppSelect @changedType="filterByArchetype"/>
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
    getCards(url = 'https://db.ygoprodeck.com/api/v7/cardinfo.php?num=20&offset=0'){
      axios.get(url)
      .then((response) => {
        console.log(response.data.data);
        this.store.cardsList = response.data.data;
      })
      .catch(function (error) {
        console.log(error);
      });

    },

    getArchetype(){
      axios.get('https://db.ygoprodeck.com/api/v7/archetypes.php')
      .then((response) => {
        console.log(response.data);
        this.store.archetypeList = response.data;
      })
      .catch(function (error) {
        console.log(error);
      });

    },

    filterByArchetype(){
      console.log("ho cambiato tipo");
      console.log(this.store.selectedArchetype.archetype_name);

      this.getCards('https://db.ygoprodeck.com/api/v7/cardinfo.php?archetype='+ this.store.selectedArchetype.archetype_name)
      

    }


  },
  created() {
    this.getCards();
    this.getArchetype();
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