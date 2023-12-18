<template lang="">
  <main>
    <AppHeader />
    <CardsList />
  </main>
</template>
<script>
import AppHeader from './components/AppHeader.vue';
import CardsList from './components/CardsList.vue'

export default {
  name: 'AppaVue',
  components: {
    AppHeader,
    CardsList
  }
}
</script>
<style lang="scss">
@use './styles/general.scss';
  
</style>