<template lang="">
    <div class="card">
        <img :src="card.card_images[0].image_url" class="card-img-top" :alt="card.name">
        <div class="card-body">
            <p class="card-text text-uppercase fw-bold">{{card.name}}</p>
            <p class="archetype">{{card.archetype}}</p>
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
<style lang="scss">
@use '../styles/partials/variables' as *;

    div.card {
        height: 100%;
    }

    div.card-body {
        background-color: $bg-color;
        color: $text-white;
        text-align: center;

        p.archetype {
            color: black;
        }
    }
</style>