<template>
    <div class="carousel">
        <slot></slot>
    </div>
</template>

<script>
import CardTypeA from "../Cards/CardTypeA.vue";
export default {
    components: { CardTypeA }
}
</script>

<style lang="sass" scoped>
.carousel 
    @apply flex flex-nowrap overflow-x-scroll p-1
        
</style>