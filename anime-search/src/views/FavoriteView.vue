<template>
  <div>
    <div v-if="animeListIsEmpty">
      <p>
        You currently do not have any favorite anime shows, consider vistiting
        our recommendation page!
      </p>
    </div>
    <div v-else>
      <h1>This is your Favorite Anime List</h1>
      <p>Go forth and watch these shows!!!</p>
      <FavoriteList :animeList="animes" />
    </div>
  </div>
</template>

<script>
import FavoriteList from "../components/FavoriteList.vue";
export default {
  name: "FavoriteView",
  components: {
    FavoriteList,
  },
  computed: {
    animes() {
      return this.$root.$data.favoriteList;
    },
    animeListIsEmpty() {
      if (this.$root.$data.favoriteList.length === 0) {
        return true;
      } else {
        return false;
      }
    },
  },
};
</script>
