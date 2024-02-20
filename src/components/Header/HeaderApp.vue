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
      
      // variabile per dare un valore da inserire
      currentImage: 0,
      // variabile per dare un valore al setInterval e al clearInterval
      autoScroll: null,

      slides: [
          {
            image: 'src/Assets/img/h-2-slider-img-11.png',
            title: 'Our new folio full of',
            word:'joy',
            text: 'Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet,consectetur, adipisci velit, sed quia non numquam eius modi.',
          },
          {
            image: 'src/Assets/img/h-2-slider-img-15.png',
            image2:'src/Assets/img/h-2-slider-img-16.png',
            title: 'Devotion that never',
            word:'ends',
            text: 'Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet,consectetur, adipisci velit, sed quia non numquam eius modi.',
          },
          {
            image: 'src/Assets/img/short-slider-rev-1-img-3.png',
            title: 'Project made with',
            word:'love',
            text: 'Neque porro quisquam est, qui dolorem ipsum quia dolor sit amet,consectetur, adipisci velit, sed quia non numquam eius modi.',
          },
          
      ],
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
    

    <SliderApp
    :propsElementSlider="slides"/>

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
    cursor: pointer;
  }
}

</style>
