<template>
  <div class="wrapper">
    <div class="products">
      <div
        class="product"
        v-for="currentAnime in animeList"
        :key="currentAnime.id"
      >
        <div class="info">
          <h1>{{ currentAnime.name }}</h1>
          <p>{{ currentAnime.character }}</p>
        </div>
        <div class="image">
          <img :src="'/images/' + currentAnime.image" />
        </div>
        <div class="price">
          <h2>{{ currentAnime.quote }}</h2>
          <button class="auto" v-on:click="addToFavoriteList(currentAnime.id)">
            <img alt="heartPic" src="/heart-shape-button.jpg" />
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
    addToFavoriteList(animeId) {
      this.$root.$data.favoriteList.push(
        this.$root.$data.animeList[animeId - 1]
      );
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

.info h1 {
  font-size: 16px;
}

.price h2 {
  font-size: 16px;
  color: white;
}

.info p {
  margin: 0px;
  font-size: 10px;
}

.price {
  display: flex;
}

.price img {
  height: 30px;
  width: 30px;
  border: none;
}

button {
  height: 50px;
  color: white;
  border: none;
}

.auto {
  margin-left: auto;
}
</style>
