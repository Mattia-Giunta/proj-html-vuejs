<script>
// import

export default {
  name: "ComponentFooterApp",
};
</script>

<template>
 
  <section>

    <div class="container">

      <div>
        <img src="../../Assets/img/logo-sidearea-1.png" alt="">
        <p>Let's Get Creative</p>
      </div>

      <div>
        <p>maree@qodeinteractive.com</p>
        <span>+44645 321 789</span>
      </div>

      <div>
        <p>Avenue d'Auderghem 10</p>
        <span>1040 Brussels, Belgium</span>
      </div>

      <div>

        <p>Stay in thouch with us</p>

        <ul>

          <li>
            <a href="">
              <i class="fa-brands fa-x-twitter"></i>
            </a>
          </li>

          <li>
            <a href="">
              <i class="fa-brands fa-pinterest-p"></i>
            </a>
          </li>

          <li>
            <a href="">
              <i class="fa-brands fa-facebook-f"></i>
            </a>
          </li>

          <li>
            <a href="">
              <i class="fa-brands fa-linkedin"></i>
            </a>
          </li>

        </ul>

      </div>


    </div>


  </section>


</template>

<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

section{
  background-color: #C0E1CF;
  padding: 50px;
  .container{
    
    width: 70%;
    margin: 0 auto;
    display: flex;
    div{
      
      flex-basis: calc(100% / 4);
      padding: 50px;
      line-height: 160%;

      ul{
        display: flex;
        list-style-type: none;
        gap: 15%;
        li{
          i{
            text-decoration: none;
            color: black;
            font-size: 20px;
          }
        }
      }
    }
  }
}



</style>
