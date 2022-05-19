<template>
  <div class="explorer">

    <!-- header -->
    <GlobalSearcher color="bg" :add="add"/>
    <GlobalHeader :PageTitle="page_title"/>
    <!-- banner -->
    <div class="banner">
    <CardTypeSearchA 
    size="md"
    :title="recent[0].title" 
    :picture="recent[0].picture"
    :program="recent[0].program"
    :author="recent[0].author"
    />
    <CardTypeSearchA
     v-for="(card, i) in recent.slice(1,recent.length)" :key="i"
     size="xs" 
     :title="card.title" 
     :picture="card.picture"
     :program="card.program"
     :author="card.author" />
    </div>



    <!-- footer -->
    <GlobalFooter :ExplorerStatus="explorer"/>
  </div>
</template>

<script>
import CardTypeA from "~/components/Cards/CardTypeA.vue";
import CardTypeSearchA from "~/components/Cards/CardTypeSearchA.vue";
import { mapState } from "vuex"
import HomeRecommendations from "~/components/Home/HomeRecommendations.vue";
import HomeDestacados from "~/components/Home/HomeDestacados.vue";
import GlobalSearcher from "../components/Global/GlobalSearcher.vue";
export default {
  name: "IndexPage",
  components: { CardTypeA, CardTypeSearchA, HomeDestacados, HomeRecommendations, GlobalSearcher},
  computed: {
    ...mapState({
      rec: state => state.home.recommendations,
      des: state => state.home.destacados,
      recent: state => state.home.recientes,
    })
  },
  data() {
    return {
      home: false,
      explorer: true,
      library: false,
      page_title: "Sigue escuchando",
      add: false
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