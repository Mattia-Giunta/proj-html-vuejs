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

    <li v-for="item in propsElementNav" :key="item">{{ item }}</li>

  </ul>

 


</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

ul{
  border: 1px solid green;
  width: 100%;
  display: flex;
  justify-content: flex-end;
  gap: 4%;
  list-style-type: none;
  padding-right: 20px;
  li{
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 2px;
  }
}

</style>