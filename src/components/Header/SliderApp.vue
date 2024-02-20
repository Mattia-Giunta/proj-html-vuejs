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
        intervalId: null // Identificatore per il setInterval
      };
    },

    methods: {
      // Funzione per cambiare l'immagine visualizzata
      changeImage(index) {
        this.currentImage = index;
      },

      // Funzione per avviare lo scorrimento automatico delle immagini
      startAutoScroll() {
        this.intervalId = setInterval(() => {
          // Incrementa l'indice dell'immagine
          this.currentImage = (this.currentImage + 1) % this.propsElementSlider.length;
        }, 2000); // Cambia immagine ogni 5 secondi (5000 millisecondi)
      },

      // Funzione per fermare lo scorrimento automatico delle immagini
      stopAutoScroll() {
        clearInterval(this.intervalId);
      }
    },

    // Funzione per passare all'immagine precedente
    prevImage() {
      this.currentImage = (this.currentImage - 1 + this.propsElementSlider.length) % this.propsElementSlider.length;
    },

    // Funzione per passare all'immagine successiva
    nextImage() {
      this.currentImage = (this.currentImage + 1) % this.propsElementSlider.length;
    },
    // Metodo che viene chiamato quando il componente viene creato
    created() {
      // Avvia lo scorrimento automatico delle immagini quando il componente viene creato
      this.startAutoScroll();
    },

    // Metodo che viene chiamato quando il componente viene distrutto
    beforeDestroy() {
      // Ferma lo scorrimento automatico delle immagini quando il componente viene distrutto
      this.stopAutoScroll();
    }
};
</script>
  






<template>
 
 <div class="container">

    <section>

      <div class="slider-left">

        <h1>{{ propsElementSlider[currentImage].title }}</h1>
        <p>{{ propsElementSlider[currentImage].text }}</p>

        <!-- Aggiungi i pulsanti per navigare tra le immagini -->
        <button @click="prevImage">Previous</button>
        <button @click="nextImage">Next</button>

      </div>

      <figure>

        
      </figure>
      
      
    </section>

  </div>

  <div>

    <img :src="`${propsElementSlider[currentImage].image}`" :alt="propsElementSlider[currentImage].title">

  </div>

</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

section{
  border: 1px solid yellow;
  height: calc(100% - 80px);
  display: flex;
  .slider-left{
    width: 50%;
    border: 1px solid red;
  }
  figure{
    width: 50%;
    border: 1px solid blue;

    img{
      display: block;
      width: 100%;
      height: 100px;
    }
  }
}
</style>