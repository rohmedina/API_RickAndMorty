<template>
  <div class="column">
    <b-card>
      <b-card-img img-alt="Image" img-top v-bind:src="character.image" v-bind:alt="character.name"> </b-card-img>
      <b-card-title>
        {{ character.name }}
      </b-card-title>
      <b-button variant="success" @click="showMore(character.id)" v-b-modal.modal-sm>Ver mas</b-button>
    </b-card>
  </div>
</template>

<script>
export default {
  props: ["character"],
  methods: {
    showMore(id) {
      this.$emit("showModal", id);
    },
  },
};
</script>
