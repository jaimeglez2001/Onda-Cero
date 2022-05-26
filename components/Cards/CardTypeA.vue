<template>
    <div :class="classes">
        <div class="bg_holder"><img src="gradient.jpg"></div>
        <div class="pic_holder"><img :src="picture"></div>
        <div class="info_holder">
            <div class="onda_logo"><img src="logo2.svg" width="24px"></div>
            <h3 class="title">{{ title }}</h3>
        </div>
    </div>
</template>

<script>

export default {
    props: {
        picture: { type: String, default: "" },
        title: { type: String, required: true },
        size: { type: String, default: "md" },
    },
    computed: {
        classes() {
            return {
                banner_xl: this.size == "xl",
                banner_sm: this.size == "sm",
                banner_md: this.size == "md",
                banner_xs: this.size == "xs",
            };
        },
    },
}
</script>

<style lang="sass" scoped>
    .banner_xs
        height: 164px
        width: 164px 
        flex-shrink: 0
        @apply bg-white relative overflow-hidden flex items-center justify-center rounded-md p-4 m-2
        .bg_holder
            @apply absolute bottom-0 left-0 w-full
            height: 66%
            img
                @apply object-cover m-0
        .pic_holder
            @apply absolute w-full h-full
            img
                @apply object-cover
        .info_holder 
            @apply flex justify-center items-center absolute overflow-visible h-full
            background: linear-gradient(360deg, rgba(0,0,0,.12) 50%, rgba(255,255,255,0) 100%)
            background-blend-mode: multiply
            @apply w-full
            @apply flex justify-center items-center
            .onda_logo
                @apply mr-2 drop-shadow-xl
                img
                    @apply drop-shadow-md
            .title
                color: #EDF7ED
                text-shadow: 2px 2px 3px rgba(0,0,0, 0.5)
                @apply font-semibold text-xl
    .banner_sm
        height: 164px
        width: 348px 
        flex-shrink: 0
        @apply bg-white relative overflow-hidden flex items-center justify-center rounded-md p-1 m-2
        .bg_holder
            @apply absolute bottom-0 left-0 w-full
            height: 66%
            img
                @apply object-contain m-0
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
                text-shadow: 2px 2px 3px rgba(0,0,0, 0.5)
                @apply font-bold text-3xl

    .banner_md
        height: 246px
        flex-basis: 100%
        @apply  bg-white relative overflow-hidden flex items-center justify-center rounded-md m-2
        .bg_holder
            @apply absolute bottom-0 left-0 w-full
            height: 66%
            img
                @apply object-contain m-0
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
                text-shadow: 2px 2px 3px rgba(0,0,0, 0.5)
                @apply font-bold text-3xl
    .banner_xl
        height: 348px
        flex-basis: 100%
        @apply bg-white relative overflow-hidden flex items-center justify-center rounded-md m-2
        .bg_holder
            @apply absolute bottom-0 left-0 w-full
            height: 66%
            img
                @apply object-contain m-0
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
                text-shadow: 2px 2px 3px rgba(0,0,0, 0.5)
                @apply font-bold text-3xl
    
    
                    
</style>