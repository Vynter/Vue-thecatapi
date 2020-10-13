<template>
  <div class="container mt-5">
    <h1 class="mt-5">Appel a une api</h1>
    <p>
      Lorem ipsum dolor sit amet consectetur adipisicing elit. Necessitatibus
      culpa ipsa reiciendis rem impedit voluptatem quod iste voluptatum,
      recusandae error molestiae in eius minima incidunt ducimus consequuntur
      illo totam aut laboriosam quasi inventore! Unde, eaque praesentium maxime
      beatae odio ab velit. Necessitatibus molestiae exercitationem accusamus
      voluptatem dicta cupiditate quo animi?
    </p>
    <img v-bind:src="urlImg" />
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "Contenu",
  data() {
    return {
      urlImg: null,
    };
  },
  methods: {},
  mounted() {
    axios
      .get("https://api.thecatapi.com/v1/images/search")
      .then((response) => (this.urlImg = response.data[0].url));
  },
};
</script>

<style scoped></style>
