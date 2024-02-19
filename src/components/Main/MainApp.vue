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
    }   
};

</script>

<template>

    <CardsApp/>
    <WorkingProcessApp/>
    <MessageAreaApp/>
    <EventCalendarApp/>

</template>


<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;


</style>