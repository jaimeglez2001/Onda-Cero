<template>
    <div class="banner">
        <div class="onda_logo"><img src="logo2.svg" width="24px"></div>
        <div class="bg_holder"><img src="gradient.jpg"></div>
        <div class="pic_holder"><img :src="picture"></div>
        <div class="info_holder">
            <h3 class="title">{{ title }}</h3>
            <span class="author">{{author}}</span>
        </div>
    </div>
</template>

<script>

export default {
    props: {
        picture: { type: String, default: "" },
        title: { type: String, required: true },
        size: { type: String, default: "md" },
        author: { type: String, required: true },
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
    .banner
        height: 164px
        width: 164px 
        flex-shrink: 0
        @apply bg-white relative overflow-hidden flex items-center justify-center rounded-md p-4 m-2
        .onda_logo
            @apply mr-2 drop-shadow-xl absolute top-2 right-0 z-20
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
            @apply flex flex-col justify-center items-center absolute
            @apply w-full
            @apply flex justify-center items-center
            .title
                color: #EDF7ED
                text-shadow: 2px 2px 3px rgba(0,0,0, 0.5)
                @apply font-semibold text-2xl text-center leading-none
            .author
                font-size: 16px
                color: #EDF7ED  
                text-shadow: 2px 2px 3px rgba(0,0,0, 0.5)
                @apply leading-none text-center
    
    
                    
</style>