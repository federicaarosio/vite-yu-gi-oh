<template lang="">
    <section id="cards">
        <h1>
            CardsList
        </h1>
        <div>
             {{ store.prova }}
        </div>
    </section>
</template>
<script>
import {store} from '../js/store.js';

export default {
    name: 'CardsList',
    data() {
        return {
            store,
        }
    },
}
</script>
<style lang="">
    
</style>