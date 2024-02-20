<script>
// import

export default {

  name: "NavbarApp",

  props:[
    'propsElementNav'
  ],

};
</script>

<template>
 
  
  

  <ul>

    <li v-for="(element,item) in propsElementNav" :key="item">{{ element }}</li>

  </ul>

 


</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

ul{
  
  width: 100%;
  display: flex;
  justify-content: flex-end;
  gap: 3%;
  list-style-type: none;
  padding-right: 40px;
  li{
    font-size: 13px;
    text-transform: uppercase;
    letter-spacing: 4px;
    font-weight: bold;
    cursor: pointer;
    &:hover{
      background-image: linear-gradient(to bottom, #ffffff 50%, #F5D8CA 50%); 
    }
  }
}

</style>