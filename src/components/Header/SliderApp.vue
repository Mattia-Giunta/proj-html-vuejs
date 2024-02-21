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
          this.autoScrollByOne('right')
        }, 4000); // Cambia immagine ogni 5 secondi (5000 millisecondi)
      },

      // Funzione per fermare lo scorrimento automatico delle immagini
      stopAutoScroll() {
        clearInterval(this.autoScroll);
      },

      // Funzione per cambiare l'immagine visualizzata
      changeImage(index) {
        this.currentImage = index;
      },

      scrollByOne(direction){

        const slider = this.$refs.slider;
        let amount = slider.offsetWidth 

        console.log(slider,amount,direction)

        if(this.currentImage === 2){
          direction = 'left'
          this.currentImage = 0
          amount = amount * 2
        }

        if(direction === 'left'){
          amount *= -1;
        }
        if(direction ==='left' && this.currentImage !== 0){

          this.currentImage --

        }else if(direction ==='right' && this.currentImage !== this.propsElementSlider.length -1){

          this.currentImage ++ 
        }

        slider.scrollBy({

          left:amount,
          behavior: 'smooth'
        })

      },

      autoScrollByOne(direction){

        const slider = this.$refs.slider;
        let amount = slider.offsetWidth 

        console.log(slider,amount,direction)

         if(this.currentImage === 2){
          direction = 'left'
          this.currentImage = 0
          amount = amount * 2
         }

        if(direction === 'left'){
          amount *= -1;
        }
        if(direction ==='left' && this.currentImage !== 0){

          this.currentImage --

        }else if(direction ==='right' && this.currentImage !== this.propsElementSlider.length -1){

          this.currentImage ++ 
        }

        slider.scrollBy({

          left:amount,
          behavior: 'smooth'
        })

      },

      scroll(index) {
            // stop autoSlider on user input 
            // clearInterval(this.autoScroll)

            const slider = this.$refs.slider;

            let amount = slider.offsetWidth;

            if (index - this.currentImage === 2 || index - this.currentImage === -2) {
                amount = amount * 2
            }
            if (index < this.currentImage) {
                amount *= -1;
            }

            this.currentImage = index
            slider.scrollBy({
                left: amount,
                behavior: 'smooth'
            });
        }

    },
};
</script>
  

<template>
 
  <div class="container">


    <i class="fa-solid fa-circle-chevron-right"
    @click="scrollByOne('right')"></i>

    <i class="fa-solid fa-circle-chevron-left"
    @click="scrollByOne('left')"></i>

    <div ref="slider" class="container-slider">

      <section 
      v-for="(element,index) in propsElementSlider"
      :key="index"
      @mouseover="stopAutoScroll"
      >

        <!-- testo carosello sinistra -->
        <div class="slider-left">

          <div>

            <h1>{{ element.title }}</h1>

            <span>{{ element.word }}</span>

            <p>{{ element.text }}</p>

            <button type="button">Read More</button>

          </div>
        
        </div>

        <!-- immagine di destra -->
        <figure>

          <img 
          :src="`${element.image}`" :alt="element.title">

          <img v-if="element.image2" :src="`${element.image2}`" :alt="element.title">
          
        </figure>
        
          
      </section>

    </div>
  

    <div class="point">  

      <i 
      v-for="(element,index) in propsElementSlider"
      :key="index"
      class="fa-solid fa-circle"
      :class=" (currentImage === index) ? 'active': ' ' "
      @click="scroll(index)"></i>

    </div>

  </div>

</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

.container-slider{
  display: flex;
  width: 100%;
  overflow-x: scroll;
  &::-webkit-scrollbar {
    display: none;
  }  /* Hide default scrollbar in WebKit browsers */


  section{
    width: 100%;
    flex-shrink: 0;
    display: flex;
    height: 600px;
    
    .slider-left{
      flex-basis: 50%;
      padding-block: 100px;
      padding-left: 300px;
      display: flex;
      justify-content: flex-end;

      div{
        
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
            color: white;
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
}

.container{
  position: relative;
  width: 100%;
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