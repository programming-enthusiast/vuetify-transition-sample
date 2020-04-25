<template>
  <div id="app">
    <v-btn @click="openModal">Open</v-btn>
    <Modal v-if="modalOpen" @close="closeModal"/>
  </div>
</template>

<script>
import Modal from "./components/Modal";

export default {
  name: "App",
  components: {
    Modal
  },
  data: () => ({
    modalOpen: false
  }),
  methods: {
    openModal() {
      this.modalOpen = true;
    },
    closeModal() {
      this.modalOpen = false;
    }
  }
};
</script>

<style lang="scss">
@import url("https://fonts.googleapis.com/css?family=Sen&display=swap");
@import "./scss/colors";

$primary-font-family: "Sen", sans-serif;

*,
*::after,
*::before {
  box-sizing: border-box;
}
html {
  height: 100%;
  background-color: $background-color;
  background-image: $background-image;
}

body,
button {
  font-family: $primary-font-family;
}
button {
  transition: all 0.2s ease-in-out;
  background: $green;
  color: #011e35;
  box-shadow: 0px 2px 0px 2px
    darken($green, 5%), 0 10px 10px 3px rgba(0, 0, 0, 0.5);
  appearance: none;
  border: 0;
  margin: 10px;
  padding: 10px 15px;
  font-size: 24px;

  &:hover {
    transform: scale(1.1);
  }

  &:active {
    transform: scale(0.9);
  }
}
</style>
