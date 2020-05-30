<template>
  <div id="inicio">
    <div class="hero">
      <h1>R&M <span>Personajes</span></h1>
      <input type="text" name="" id="" />
      <button class="btn btn-success btn" v-on:click="fetch">Consultar</button>
    </div>
    <div class="container">
      <Character v-for="character of characters" v-bind:key="character.id" v-bind:character="character" />
    </div>
  </div>
</template>

<script>
import axios from "axios";

import Character from "@/components/Character.vue";

export default {
  name: "inicio",
  components: { Character },
  data: function() {
    return {
      characters: [],
    };
  },
  created() {
    this.fetch();
  },
  methods: {
    fetch() {
      let result = axios
        .get("https://rickandmortyapi.com/api/character")
        .then((res) => {
          this.characters = res.data.results;
          console.log(res.data);
        })
        .catch((err) => {
          console.log(err);
        });
    },
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
  width: 150px;
  padding: 1em;
}
</style>
