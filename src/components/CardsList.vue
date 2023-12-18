<template lang="">
    <section id="cards" class="container bg-white p-5">
        <section class="bg-dark text-white container fs-6 fw-bold py-3 px-5">Found</section>
        <div class="row">

            <article v-for="card in cardsList" :key="card.id" class="col-2 mb-5">
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
<style lang="scss">
    
</style>