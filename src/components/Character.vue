<template>
  <div>
    <div>
      <img v-bind:src="character.image" v-bind:alt="character.name" />
    </div>
    <div>
      <h3>{{ character.name }}</h3>
    </div>
  </div>
</template>

<script>
export default {
  props: ["character"],
};
</script>
