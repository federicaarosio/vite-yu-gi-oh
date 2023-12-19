<template>
        <section class="bg-dark text-white container fs-6 fw-bold py-3 px-5">Found {{store.cardsList.length}} cards </section>
</template>
<script>
import { store } from '../js/store.js';
export default {
    data() {
        return {
            store
        }
    },
}
</script>
<style lang="scss">
    
</style>