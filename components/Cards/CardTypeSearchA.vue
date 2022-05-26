<template>
    <div :class="classes">
        <div class="pic_holder"><img :src="picture"></div>
        <div class="info_holder">
            <div class="program_holder">
                <h3 class="title">{{ title }}</h3>
                <h3 class="program">{{ program }}</h3>
            </div>
            <span class="author">{{ author }}</span>
        </div>
        <div class="progress_holder">
            <div class="progress_bar">
                <div class="progressed"></div>
            </div>
        </div>

    </div>
</template>

<script>

export default {
    props: {
        picture: { type: String, required: true },
        title: { type: String, required: true },
        size: { type: String, default: "md" },
        program: { type: String, required: true },
        author: { type: String, required: true },

    },
    computed: {
        classes() {
            return {
                banner_md: this.size == "md",
                banner_xs: this.size == "xs"

            };
        },
    },
}
</script>

<style lang="sass" scoped>
    .banner_md
        height: 220px
        flex-basis: 100%
        @apply relative overflow-hidden flex items-center justify-center rounded-md p-4 m-2 px-5 mb-5
        .pic_holder
            @apply absolute 
            img
                @apply object-cover 
        .info_holder 
            @apply flex flex-col justify-center items-center absolute
            @apply w-full h-full
            @apply flex justify-center items-center
            background: linear-gradient(360deg, rgba(0,0,0,.12) 50%, rgba(255,255,255,0) 100%)
            .program_holder
                @apply flex
                .title
                    color: #EDF7ED
                    text-shadow: 2px 2px 3px rgba(0,0,0, 0.5)
                    @apply font-semibold text-2xl mr-3 mb-0
                .program
                    color: #EDF7ED
                    text-shadow: 2px 2px 3px rgba(0,0,0, 0.5)
                    @apply font-semibold text-2xl mb-0
            .author
                @apply text-white text-sm m-0
        .progress_holder
            @apply px-4 absolute bottom-4 left-0 w-full drop-shadow-xl z-10
            .progress_bar
                background-color: rgba( 94, 94 , 94 , .2)
                @apply w-full h-2 z-10 rounded-full  overflow-hidden drop-shadow-xl
                .progressed
                    background-color: #42ec42
                    @apply w-20 h-2 rounded-full
.banner_xs
        height: 72px
        flex-basis: 100%
        @apply relative overflow-hidden flex items-center justify-center rounded-md p-4 m-2 px-5 mb-5
        .pic_holder
            @apply absolute 
            img
                @apply object-cover 
        .info_holder 
            @apply flex flex-col justify-center items-center absolute pb-2
            @apply w-full h-full
            @apply flex justify-center items-center
            background: linear-gradient(360deg, rgba(0,0,0,.2) 75%, rgba(255,255,255,0) 100%)
            .program_holder
                @apply flex
                .title
                    color: #EDF7ED
                    text-shadow: 2px 2px 3px rgba(0,0,0, 0.5)
                    @apply font-semibold text-2xl mr-3 mb-0
                .program
                    color: #EDF7ED
                    text-shadow: 2px 2px 3px rgba(0,0,0, 0.5)
                    @apply font-semibold text-2xl mb-0
            .author
                @apply text-white text-sm m-0
                text-shadow: 2px 2px 3px rgba(0,0,0, 0.5)
        .progress_holder
            @apply px-4 absolute bottom-1 left-0 w-full drop-shadow-xl z-10
            .progress_bar
                background-color: rgba( 94, 94 , 94 , .2)
                @apply w-full h-2 z-10 rounded-full  overflow-hidden drop-shadow-xl
                .progressed
                    background-color: #42ec42
                    @apply w-20 h-2 rounded-full
                
                    
</style>