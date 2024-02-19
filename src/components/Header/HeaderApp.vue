<script>
// import
import NavbarApp from '../Header/NavbarApp.vue';
import SliderApp from '../Header/SliderApp.vue';

export default {
  name: "HeaderApp",

  components: {
    NavbarApp,
    SliderApp,
  },
};
</script>

<template>
 
  <NavbarApp/>

  <SliderApp/>


</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;


</style>
