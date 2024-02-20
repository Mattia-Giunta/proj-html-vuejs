<script>
// import

export default {

  name: "SliderApp",

    props: {

      propsElementSlider: {
        
        type: Array,
        requiured: true,
      }
  
    },

    data() {
      return {
        currentImage: 0, // Indice dell'immagine attualmente visualizzata
        autoScroll: null // Identificatore per il setInterval
      };
    },


    // Metodo che viene chiamato quando il componente viene creato
    created() {
      // Avvia lo scorrimento automatico delle immagini quando il componente viene creato
      this.startAutoScroll();
    },


    methods: {

      // Funzione per passare all'immagine precedente
      prevImage() {
        this.currentImage = (this.currentImage - 1 + this.propsElementSlider.length) % this.propsElementSlider.length;
      },

      // Funzione per passare all'immagine successiva
      nextImage() {
        this.currentImage = (this.currentImage + 1) % this.propsElementSlider.length;
      },

      // Funzione per avviare lo scorrimento automatico delle immagini
      startAutoScroll() {
        this.autoScroll = setInterval(() => {
          // Incrementa l'indice dell'immagine
          this.prevImage()
        }, 2000); // Cambia immagine ogni 5 secondi (5000 millisecondi)
      },

      // Funzione per fermare lo scorrimento automatico delle immagini
      stopAutoScroll() {
        clearInterval(this.autoScroll);
      },

      // Funzione per cambiare l'immagine visualizzata
      changeImage(index) {
        this.currentImage = index;
      },

    },
};
</script>
  

<template>
 
  <div class="container">


    <i class="fa-solid fa-circle-chevron-right"
    @click="nextImage"></i>

    <i class="fa-solid fa-circle-chevron-left"
    @click="prevImage"></i>

    <section

    @mouseover="stopAutoScroll"

    @mouseleave="startAutoScroll">

      <!-- testo carosello sinistra -->
      <div class="slider-left">

        <div>

          <h1>{{ propsElementSlider[currentImage].title }}</h1>

          <span>{{ propsElementSlider[currentImage].word }}</span>

          <p>{{ propsElementSlider[currentImage].text }}</p>

          <button type="button">Read More</button>

        </div>
      
      </div>

      <!-- immagine di destra -->
      <figure>

        <img 
        :src="`${propsElementSlider[currentImage].image}`" :alt="propsElementSlider[currentImage].title">

        <img v-if="propsElementSlider[currentImage].image2" :src="`${propsElementSlider[currentImage].image2}`" :alt="propsElementSlider[currentImage].title">
        
      </figure>
      
        
    </section>

  

    <div class="point">  

      <i 
      v-for="(element,index) in propsElementSlider"
      :key="index"
      class="fa-solid fa-circle"
      :class=" (currentImage === index) ? 'active': ' ' "
      @click="changeImage(index)"></i>

    </div>

  </div>

</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;


section{
  
  height: 600px;
  display: flex;
  transition: transform 0.5s ease;
  
    
  
  .slider-left{
    width: 50%;
    
    padding-block: 100px;
    display: flex;
    justify-content: flex-end;
    div{
      
      width: 70%;
      
      h1{
        font-weight: 300;
        font-size: 90px;
        display: inline;
        
      }
      span{
        font-size: 90px;
        font-family: "Playfair Display", serif;
        font-optical-sizing: auto;
        font-weight: 500;
        font-style: normal;
        margin-left: 5%;
      }
      p{
        font-size: 20px;
      }
      button{
        margin-top: 20px;
        padding: 15px 50px;
        text-transform: uppercase;
        border: 3px solid #E1C0B0;
        background: none;
        font: inherit;
        font-weight: bold;
        font-size: 15px;
        color: inherit;
        cursor: pointer;
        letter-spacing: 4px;
        transition: background 0.3s ease-in-out;
        &:hover{
          background-color: #E1C0B0;
        }
      }
    
    }
  
  }
  figure{
    width: 50%;
    display: flex;
    align-items: center;
    
    padding: 50px;
    justify-content: center;
    img{
      
      display: block;
      height: 100%;
    }
  }
}

.container{
  position: relative;
  .fa-circle-chevron-right{
    position: absolute;
    right: 20px;
    top: 50%;
    cursor: pointer;
    z-index: 999;
    font-size: 30px;
    color: #E1C0B0;
  }
  .fa-circle-chevron-left{
    position: absolute;
    left: 20px;
    top: 50%;
    cursor: pointer;
    z-index: 999;
    font-size: 30px;
    color: #E1C0B0;
  }
}
.point{
  
  display: flex;
  justify-content: center;
  gap: 20px;
  i{
    font-size: 10px;
    color: #E1C0B0;
    cursor: pointer;
    
  }
}

.active{
  scale: 150%;
}

</style>