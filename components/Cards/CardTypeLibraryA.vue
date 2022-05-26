<template>
    <div class="banner">
        <div class="pic_holder"><img :src="picture"></div>
        <div class="info_holder">
            <h3 class="title_green w-full h-full flex justify-center items-center text-center bg-white" v-if="WhiteBg == true">{{ title }}</h3>
            <h3 class="title_white" v-else-if="picture == `gradient.jpg`">{{ title }}</h3>
            <h3 class="title" v-else>{{ title }}</h3>
        </div>
    </div>
</template>

<script>

export default {
    props: {
        picture: { type: String, default: "" },
        title: { type: String, required: true },
        size: { type: String, default: "md" },
        WhiteBg: { type: Boolean, default: "false" },
    },
}
</script>

<style lang="sass" scoped>
    .banner
        height: 164px
        flex-basis: 100%
        @apply  relative overflow-hidden flex items-center justify-center rounded-md m-2 mb-5 bg-white
        .pic_holder
            @apply absolute 
            img
                @apply object-cover 
        .info_holder 
            @apply flex justify-center items-center absolute
            @apply w-full h-full
            @apply flex justify-center items-center
            background: linear-gradient(360deg, rgba(0,0,0,.12) 50%, rgba(255,255,255,0) 100%)
            .onda_logo
                @apply mr-2 drop-shadow-xl
            .title
                color: #EDF7ED
                text-shadow: 2px 2px 8px rgba(0,0,0, 0.8)
                @apply font-semibold text-3xl
            .title_green
                color: #42EC42
                @apply font-semibold text-3xl
            .title_white
                color: #EDF7ED
                @apply font-semibold text-3xl
</style>