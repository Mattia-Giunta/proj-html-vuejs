<script>



export default {
    name: "MessageAreaApp",      
};

</script>

<template>

<section>

    <div>
        <h1>Whant to work with us? Send us </h1>
        <span>a message!</span>

        <p>Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commo.</p>

        <div class="btn-lignt-green">Contact</div>

    </div>

</section>

</template>


<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

section{
    text-align: center;
    background-image: url(../../Assets/img/h-2-background-1.jpg);
    background-repeat: no-repeat;
    background-size: cover;
    padding-block: 150px;
    div{

        width: 70%;
        margin: 0 auto;
        h1{
            
            font-weight: 300;
            font-size: 60px;
            display: inline;
        
        }
        span{
            font-size: 60px;
            font-family: "Playfair Display", serif;
            font-optical-sizing: auto;
            font-weight: 500;
            font-style: normal;
            
        }
        p{
            font-size: 20px;
            padding-block: 30px;
        }
        .btn-lignt-green{
            margin: 0 auto;
            background-color: #D8F0E3;
            width: 14%;
            padding-block: 20px ;
            text-transform: uppercase;
            letter-spacing: 3px;
            font-size: 12px;
            font-weight: bold;
            cursor: pointer;
            transition: background 0.3s ease-in-out;
            &:hover{
                background-color: #E1C0B0;
                color: white;

            }
        }
    }
}

</style>