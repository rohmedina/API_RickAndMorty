<template>
  <div class="column">
    <div class="card">
      <img v-bind:src="character.image" v-bind:alt="character.name" />
      <div class="card-content">
        <h3 class="title">{{ character.name }}</h3>
        <button class="btn btn-success btn">Ver mas</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["character"],
};
</script>
