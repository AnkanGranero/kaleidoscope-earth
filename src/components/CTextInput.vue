<template>
  <input class="CtextInput" type="text" v-model="textInput" :placeholder="textPlaceholder" />
</template>

<script>
export default {
  name: "CTextInput",
  props: {
    textPlaceholder: {
      type: String,
      default: ""
    }
  },
  data() {
    return {
      textInput: ""
    };
  }
};
</script>


<style>
.CtextInput {
  height: 50px;
  border-radius: 7px;
  border: 1px solid black;
  width: 450px;
  display: inline;
  font-size: 20px;
  padding-left: 20px;
}
</style>