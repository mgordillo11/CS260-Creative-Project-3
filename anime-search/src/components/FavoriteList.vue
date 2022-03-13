<template>
  <div class="wrapper">
    <div class="products">
      <div
        class="product"
        v-for="currentAnime in animeList"
        :key="currentAnime.id"
      >
        <div class="info">
          <h1>Anime: {{ currentAnime.name }}</h1>
          <p>Character: {{ currentAnime.character }}</p>
        </div>
        <div class="image">
          <img :src="'/images/' + currentAnime.image" />
        </div>
        <div class="price">
          <h2>Quote: {{ currentAnime.quote }}</h2>
          <button
            class="auto"
            v-on:click="deleteFromFavoriteList(currentAnime.id)"
          >
            Unfollow
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "AnimeList",
  props: {
    animeList: Array,
  },
  methods: {
    deleteFromFavoriteList(animeId) {
      let currentAnimeItem = 0;
      while (this.$root.$data.favoriteList.length > currentAnimeItem) {
        if (this.$root.$data.favoriteList[currentAnimeItem].id === animeId) {
          this.$root.$data.favoriteList.splice(currentAnimeItem, 1);
          break;
        } else {
          currentAnimeItem++;
        }
      }
    },
  },
};
</script>

<style scoped>
.wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}

.products {
  margin-top: 20px;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-around;
}

.product {
  margin: 10px;
  margin-top: 50px;
  width: 200px;
}

.product img {
  border: 2px solid #333;
  height: 250px;
  width: 200px;
  object-fit: cover;
}

.product .image {
  display: flex;
  justify-content: center;
  margin-bottom: 5px;
}

.info {
  background: #f2921d;
  color: #000;
  padding: 10px 30px;
  height: 80px;
}

.info p {
  font-size: 10px;
}

.info h1 {
  font-size: 16px;
}

.price h2 {
  font-size: 16px;
  color: black;
}

.info p {
  font-size: 12px;
  font-style: italic;
}

.price {
  display: flex;
  flex-direction: column;
}

.price img {
  height: 30px;
  width: 30px;
  border: none;
}

button {
  height: 50px;
  color: black;
  border: none;
}

.auto {
  justify-content: center;
}
</style>
