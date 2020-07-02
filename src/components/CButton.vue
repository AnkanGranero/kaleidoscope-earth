<template>
  <button v-on:click="$emit('clicked');" class="CButton">
    <router-link class="CButton__router" v-if="routerLink" :to="routerLink">{{ msg}}</router-link>
    <span v-else>{{ msg }}</span>
  </button>
</template>

<script>
export default {
  name: "CButton",
  props: {
    msg: String,
    size: {
      type: String,
      default: "medium"
    },
    routerLink: {
      type: String,
      default: ""
    }
  },
  methods: {}
};
</script>

<style lang="scss" scoped>
@import url("https://fonts.googleapis.com/css2?family=Open+Sans:wght@400;600&display=swap");

.CButton {
  font-family: "Open Sans", sans-serif;
  width: 450px;
  height: 68px;
  border-radius: 35px;
  background-color: rgb(132, 184, 71);
  border: none;
  color: white;
  font-size: 18px;
  font-weight: 600;
  text-decoration: none;

  &:focus {
    outline: 1px solid transparent;
    outline-offset: -4px;
  }

  &:active {
    transform: scale(0.99);
  }

  &__router {
    text-decoration: none;
    color: inherit;
  }
}
</style>

