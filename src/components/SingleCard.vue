<template lang="">
    <div class="card">
        <img :src="card.card_images[0].image_url" class="card-img-top" :alt="card.name">
        <div class="card-body">
            <p class="card-text">{{card.name}}</p>
        </div>
    </div>
</template>
<script>
export default {
    props: {
        card: {
            type: Object,
            required: true,
        }
    }
}
</script>
<style lang="">
    
</style>