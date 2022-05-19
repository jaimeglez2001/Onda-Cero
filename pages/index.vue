<template>
  <div class="index">

    <!-- header -->
    <HomeHeader ProfPic="" />

    <!-- banner -->
    <div class="banner">
    <CardTypeA size="md" title="Para ti" picture="banner_4.jpg" />
    </div>

    <!-- reccomendations -->
    <HomeRecommendations>
      <CardTypeA 
      v-for="(card, i) in rec" :key="i" 
      size="xs" 
      :title="card.title" 
      :picture="card.picture" 
      />
    </HomeRecommendations>
    <HomeDestacados>
      <CardTypeA size="sm" title="Destacados" picture="banner_9.jpg" />
      <CardTypeB 
      v-for="(card, i) in des" :key="i" 
      size="xs" 
      :title="card.title" 
      :picture="card.picture"
      :author="card.author"
      />
    </HomeDestacados>
    <div class="novedades">
      <CardTypeA size="xl" title="Novedades" picture="banner2wh.jpg" />
    </div>

    <!-- news -->

    <!-- keepListening -->

    <!-- footer -->
    <GlobalFooter :HomeStatus="home"/>
  </div>
</template>

<script>
import CardTypeA from "~/components/Cards/CardTypeA.vue";
import { mapState } from "vuex"
import HomeRecommendations from "~/components/Home/HomeRecommendations.vue";
import HomeDestacados from "~/components/Home/HomeDestacados.vue";
import CardTypeB from "~/components/Cards/CardTypeB.vue";
export default {
  name: "IndexPage",
  components: { CardTypeA, HomeDestacados, HomeRecommendations, CardTypeB },
  computed: {
    ...mapState({
      rec: state => state.home.recommendations,
      des: state => state.home.destacados
    })
  },
  data() {
    return {
      home: true,
      explorer:false,
    }
  }
};
</script>


<style lang="sass" scoped>
  .index 
    min-height: 100vh
    background-image: url("/background.png")
    background-repeat: no-repeat
    background-size: cover
    background-attachment: fixed
    @apply pb-20
    .banner 
      @apply p-1
    .novedades
      @apply p-1
</style>