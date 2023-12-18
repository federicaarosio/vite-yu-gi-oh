<template lang="">
    <section id="cards" class="container">
        <div class="row">
            <!-- TODO: component per la singola card -->
            <article v-for="card in cardsList" :key="card.id" class="col-12 col-md-4 col-lg-2 mb-4">
                <SingleCard :card="card" />
            </article>
        </div>
        
    </section>
</template>
<script>
import {store} from '../js/store.js';
import SingleCard from './SingleCard.vue';

export default {
    name: 'CardsList',
    data() {
        return {
            store,
        }
    },

    components: {
        SingleCard
    },

    props: {
        cardsList: {
            type: Array,
        }
    }
}
</script>
<style lang="">
    
</style>