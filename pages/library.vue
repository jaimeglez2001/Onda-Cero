<template>
  <div class="explorer">

    <!-- header -->
    <GlobalSearcher color="tr" :add="add"/>
    <GlobalHeader :PageTitle="page_title"/>
    <!-- banner -->
    <div class="banner">
    <CardTypeLibraryA
     v-for="(card, i) in lib" :key="i"
     :title="card.title" 
     :picture="card.picture"
     :program="card.program"
     :author="card.author" 
     :WhiteBg="card.white" />
    </div>



    <!-- footer -->
    <GlobalFooter :LibraryStatus="library"/>
  </div>
</template>

<script>
import CardTypeLibraryA from "~/components/Cards/CardTypeLibraryA.vue";
import { mapState } from "vuex"
import GlobalSearcher from "../components/Global/GlobalSearcher.vue";
export default {
  name: "IndexPage",
  components: { CardTypeLibraryA, GlobalSearcher},
  computed: {
    ...mapState({
      lib: state => state.home.libraries,
    })
  },
  data() {
    return {
      home: false,
      explorer: false,
      library: true,
      page_title: "Mi biblioteca",
      add: true
    }
  }
};
</script>


<style lang="sass" scoped>
  .explorer 
    min-height: 100vh
    background-image: url("/bg2.png")
    background-repeat: no-repeat
    background-size: cover
    background-attachment: fixed
    @apply pb-20 pt-16
    .banner 
      @apply p-1
    .novedades
      @apply p-1
</style>