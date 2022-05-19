<template>
  <header :class="classes">
    <div class="search_holder">
      <div class="searchbar">
        <form>
        <svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="#EDF7ED" viewBox="0 0 256 256"><rect width="256" height="256" fill="none"></rect><circle cx="116" cy="116" r="84" fill="none" stroke="#EDF7ED" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></circle><line x1="175.4" y1="175.4" x2="224" y2="224" fill="none" stroke="#EDF7ED" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></line></svg>          
        <input type="text" placeholder="Buscar">
        </form>
      </div>
    </div>
    <span>Cancelar</span>
    <svg v-if="add == true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="#ffffff" viewBox="0 0 256 256"><rect width="24" height="24" fill="none"></rect><line x1="40" y1="128" x2="216" y2="128" fill="none" stroke="#ffffff" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></line><line x1="128" y1="40" x2="128" y2="216" fill="none" stroke="#ffffff" stroke-linecap="round" stroke-linejoin="round" stroke-width="16"></line></svg>
  </header>
</template>

<script>
export default {
  props:{
    color: { type: String, default: "bg" },
    add: { type: Boolean, default: false }
  },
   computed: {
        classes() {
            return {
                searcher_bg: this.color == "bg",
                searcher_tr: this.color == "tr"

            };
        },
    },
}
</script>

<style lang="sass" scoped>
  .searcher_bg
    background-color: #2D372C
    @apply flex items-center w-full p-5 justify-between fixed top-0 right-0 z-50
    .search_holder
      @apply flex items-center w-full
      .searchbar 
        background-color: #535D52
        @apply w-full rounded-md h-7 items-center flex
        form
          @apply flex items-center p-4
          svg
            @apply opacity-20
          input
            @apply outline-none w-full bg-transparent pl-2
    span
      @apply text-white ml-4 mr-4
  .searcher_tr
    @apply flex items-center w-full p-5 justify-between fixed top-0 right-0 z-50
    backdrop-filter: blur(16px)
    .search_holder
      @apply flex items-center w-full
      .searchbar 
        background-color: rgba(237,247 ,237 ,0.2 )
        @apply w-full rounded-md h-7 items-center flex
        form
          @apply flex items-center p-4
          svg
            @apply opacity-50
          input
            @apply outline-none w-full bg-transparent pl-2 text-white
            ::placeholder
              color: white
    span
      @apply text-white ml-4 mr-4
    
</style>