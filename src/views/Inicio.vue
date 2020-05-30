<template>
  <div id="inicio">
    <h1>R&M <span>Personajes</span></h1>

    <div class="card" v-for="character in characters" v-bind:key="character.id">
      <img v-bind:src="character.image" v-bind:alt="character.name" />
      <div class="card-body">
        <h2 class="card-title">{{ character.name }}</h2>
      </div>
    </div>
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "inicio",
  data() {
    return {
      characters: [],
    };
  },
  mounted() {
    let vue = this;
    axios.get("https://rickandmortyapi.com/api/character/").then(function(response) {
      vue.characters = response.data.results;
      console.log(vue.characters);
    });
  },
};
</script>

<style>
body {
  background-image: url("https://rickandmortypod.com/wp-content/uploads/2018/11/cropped-RM_page-header_background1-3.png");
  background-size: cover;
  background-repeat: no-repeat;
}
.card {
  display: flex;
  align-items: center;
  padding: 1em;
}
.card-title {
  text-align: center;
  padding: 30px;
}
h1,
h2 {
  color: rgb(68, 168, 68);
}
span {
  color: white;
}
img {
  border-radius: 50%;
  width: 150px;
  padding: 1em;
}
</style>
