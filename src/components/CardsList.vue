<template lang="">
    <section id="cards" class="container bg-white p-5">
        <section class="bg-dark text-white container fs-6 fw-bold py-3 px-5">Found</section>
        <div class="row d-flex">

            <article v-for="card in store.cardsList" :key="card.id" class="mb-4">
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

    // props: {
    //     cardsList: {
    //         type: Array,
    //     }
    // }
}
</script>
<style lang="scss">
    .row {

        article {
            width: calc(100% / 5);
        }
    }
</style>