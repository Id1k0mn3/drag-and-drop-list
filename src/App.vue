<template>
  <base-container title="Vuex"></base-container>
  <button-add-section></button-add-section>
</template>

<script>
import BaseContainer from './components/BaseContainer.vue';
import ButtonAddSection from './components/ButtonAddSection.vue';

export default {
  components: {
    BaseContainer,
    ButtonAddSection,
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}

html {
  font-family: sans-serif;
}

body {
  margin: 0;
}
</style>