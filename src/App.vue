<script>
// import
import HeaderApp from "./components/Header/HeaderApp.vue";
import MainApp from "./components/Main/MainApp.vue";
import FooterApp from "./components/Footer/FooterApp.vue"

import { store } from "./store";
// import axios from "axios";

export default {

  components: {
    HeaderApp,
    MainApp,
    FooterApp
  },

  data() {
    return {
      store,
    };
  },

  created() {
    
  },

  methods: {
    
  },
};
</script>

<template>
  
  <HeaderApp/>

  <MainApp/>

  <FooterApp/>


</template>

<style lang="scss">
@use "./styles/general.scss";


</style>
