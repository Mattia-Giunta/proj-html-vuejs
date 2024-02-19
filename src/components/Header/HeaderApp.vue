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

  data() {
    return {
      nav: ['home', 'pages', 'portfolio', 'blog', 'shop', 'element'],
      
    };
  },
  

  

};
</script>

<template>
 
  <header>

    <nav>

      <img src="../../Assets/img/logo-sidearea-1.png" alt="">

      <NavbarApp 
      :propsElementNav="nav"/>
     
      
      
      <img src="../../Assets/svg/svg-1.svg" alt="">

    </nav>
    

    <SliderApp/>

  </header>

</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

nav{
  padding: 30px;
  display: flex;
  justify-content: space-between;
  align-items: center;
  img{
    display: block;
    max-width: 100%;
  }
}

</style>
