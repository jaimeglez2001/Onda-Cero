<template>
    <div class="ctos_holder">
      <div class="ctos">
        <div class="home" v-if="HomeStatus == true">
           <nuxt-link to="/"><img src="onda_cero-15.png" width="32px"></nuxt-link> 
        </div>
        <div class="home" v-else>
           <nuxt-link to="/"><img src="onda_cero-11.svg" width="32px"></nuxt-link> 
        </div>
        <div class="explorer" v-if="ExplorerStatus == true">
          <nuxt-link to="/explore"><img src="onda_cero-16.png" width="32px"></nuxt-link> 
        </div>
        <div class="explorer" v-else>
           <nuxt-link to="/explore"><img src="onda_cero-12.svg" width="32px"></nuxt-link> 
        </div>
        <div class="library" v-if="LibraryStatus == true">
           <nuxt-link to="/library"><img src="onda_cero-17.png" width="32px"></nuxt-link> 
        </div>
        <div class="library" v-else>
           <nuxt-link to="/library"><img src="onda_cero-13.svg" width="32px"></nuxt-link> 
        </div>
        <div class="radio" v-if="RadioStatus == true">
           <nuxt-link to=""><img src="onda_cero-18.png" width="32px"></nuxt-link> 
        </div>
        <div class="radio" v-else>
           <nuxt-link to=""> <img src="onda_cero-14.svg" width="32px"></nuxt-link> 
        </div>
      </div>
    </div>
</template>

<script>
export default {
  props: {
    HomeStatus: { type: Boolean, default: false },
    ExplorerStatus: { type: Boolean, default: false },
    LibraryStatus: { type: Boolean, default: false },
    RadioStatus: { type: Boolean, default: false }
  }
};
</script>

<style lang="sass" scoped>
.ctos_holder
  background-color: rgba(45,55,44, 0.2)
  backdrop-filter: blur(16px)
  @apply flex w-full justify-center p-4 z-20
  @apply fixed bottom-0 left-0
  .ctos
    @apply flex items-center justify-between w-full p-2
    .home
      img
        fill: red !important
  

    
</style>