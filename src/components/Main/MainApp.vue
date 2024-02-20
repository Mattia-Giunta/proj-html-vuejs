<script>
import CardsApp from './CardsApp.vue';
import WorkingProcessApp from './WorkingProcessApp.vue';
import MessageAreaApp from './MessageAreaApp.vue';
import EventCalendarApp from './EventCalendarApp.vue';


export default {
    name: "MainApp",  
    components: {
        CardsApp,
        WorkingProcessApp,
        MessageAreaApp,
        EventCalendarApp,
    }, 
    
    data() {
    return {

     
      cardsBlog: [
          {
            image: 'src/assets/img/h-2-blog-img-1.jpg',
            title: 'This way, loves: a detailed guide through new design',
            author:'Emily Fields',
            date: 'may 19',
          },
          {
            image: 'src/assets/img/h-2-blog-img-2.jpg',
            title: 'I try to give people a different way of looking art',
            author:'Emily Fields',
            date: 'may 19',
          },
          {
            image: 'src/assets/img/h-2-blog-img-3.jpg',
            title: 'Introduce Richard Laperrière of those amazing feature',
            author:'Emily Fields',
            date: 'may 19',
          },
          
      ],
    };
  },
};

</script>

<template>

    <CardsApp/>
    <WorkingProcessApp/>
    <MessageAreaApp/>
    <EventCalendarApp
    :propsElementBlog="cardsBlog"/>

</template>


<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;


</style>