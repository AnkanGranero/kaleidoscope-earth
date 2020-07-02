<template>
  <div id="app">
    <div id="app__nav">
      <div class="app__slider">
        <transition name="slide-fade">
          <CTextInput v-if="show" :text-placeholder="placeholder" />
        </transition>
      </div>
      <transition name="slide-fade">
        <CButton v-if="show" @clicked="toggleOption" :msg="msg"></CButton>
      </transition>
    </div>
  </div>
</template>
<script>
import CButton from "./components/CButton";
import CTextInput from "./components/CTextInput";
export default {
  name: "App",
  components: {
    CButton,
    CTextInput
  },
  data() {
    return {
      show: true,
      placeholder: "Email adress",
      placeholderArray: ["Full name", "country", "company"],
      msgArray: ["Continue"],
      msg: "Get started",
      clicks: 0
    };
  },
  methods: {
    toggleOption() {
      let index = this.clicks % 3;
      this.show = !this.show;
      setTimeout(() => {
        this.placeholder = this.placeholderArray[index];
        this.msg = this.msgArray[0];
        this.show = !this.show;
        this.clicks += 1;
      }, 1000);
    }
  }
};
</script>

<style lang="scss" scoped>
#app {
  height: 100%;
  width: 100%;
  position: absolute;
  margin: 0;
  top: 0;
  left: 0;
  display: flex;
  justify-content: center;
  align-items: center;

  .slide-fade-enter-active {
    transition: all 1s linear;
  }
  .slide-fade-leave-active {
    transition: all 1s linear;
  }
  .slide-fade-leave-to
/* .slide-fade-leave-active below version 2.1.8 */ {
    transform: translateX(-200%);
    opacity: 0.5;
  }
  .slide-fade-enter {
    transform: translateX(200%);
    opacity: 0;
  }

  &__nav {
    display: flex;
    flex-direction: column;
    width: 100%;
    align-items: center;
    justify-content: space-evenly;
    height: 50%;
  }
  &__slider {
    width: 100%;
  }
}
</style>
