<template lang="">
    <div class="container mb-4">
        <select name="select" id="select" class="p-2"  @change="$emit('changedType', selectedArchetype)" v-model="store.selectedArchetype">
            <option v-for="archetype in store.archetypeList" :value="archetype">{{ archetype.archetype_name }}</option>
        </select>
    </div>
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