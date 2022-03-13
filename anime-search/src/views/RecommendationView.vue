<template>
  <div>
    <h1>These are the 5 Anime shows we recommend you watch soon!</h1>
    <h2>Adding them to your list of favorites might cheer you up!</h2>
    <AnimeList :animeList="animes" />
  </div>
</template>

<script>
import AnimeList from "../components/AnimeList.vue";
export default {
  name: "RecommendationView",
  components: {
    AnimeList,
  },
  data() {
    return {
      searchText: "",
    };
  },
  computed: {
    animes() {
      return this.$root.$data.animeList.filter((anime) => anime.id % 2 === 0);
    },
  },
};
</script>
