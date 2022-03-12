<template>
  <div class="wrapper">
    <div class="products">
      <div
        class="product"
        v-for="currentAnime in animeList"
        :key="currentAnime.id"
      >
        <div class="info">
          <h1>{{ currentAnime.animeName }}</h1>
          <p>{{ currentAnime.character }}</p>
          <p>{{ currentAnime.quote }}</p>
        </div>
        <div class="image">
          <img :src="'/images/' + anime.image" />
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
};
</script>

<style>
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

.info p {
  margin: 0px;
  font-size: 10px;
}
</style>
