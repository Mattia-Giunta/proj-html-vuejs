<script>



export default {
    name: "EventCalendarApp",

    props:[
    'propsElementBlog'
  ],
};

</script>

<template>

    <section>



        <div class="blog-container">

            <figure
            v-for="(element,item) in propsElementBlog" 
            :key="item">
                <div>
                    <i class="fa-sharp fa-solid fa-bookmark"></i>

                    <h1>07</h1>
                    <span>{{element.date}}</span>

                    <div class="image-container">
                        <img 
                        :src="`${element.image}`"
                        :alt="element.title">
                    </div>
                    
                </div>    

                <h1>{{element.title}}</h1>

                <p>By {{element.author }}</p>

            </figure>

            

        </div>
        




    </section>
    

</template>


<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

section{
   padding-block: 150px;
    
   .blog-container{
        flex-basis: calc(100% / 3);
        
        margin: 0 auto;
        display: flex; 
        width: 70%;
        gap: 30px;
        figure{
            div{
                
                position: relative;
                i{
                    position: absolute;
                    font-size: 80px;
                    left: 20px;
                    top: -20px;
                    background-image: linear-gradient(to bottom, #C0E1CF 55%, #F3D0C7 45%);
                    -webkit-background-clip: text;
                    background-clip: text;
                    color: transparent;
                    z-index: 999;
                }
                h1{
                    position: absolute;
                    font-family: "Playfair Display", serif;
                    font-optical-sizing: auto;
                    font-weight: 500;
                    font-style: normal; 
                    font-size: 40px;
                    left: 30px;
                    top: -50px;
                    z-index: 999;
                }
                span{
                    position: absolute;
                    left: 30px;
                    top: 25px;
                    text-transform: uppercase;
                    font-size: 11px;
                    font-weight: bold;
                    z-index: 999;
                }
                .image-container{
                    overflow: hidden;
                }
                img{
                display: inline-block;
                border: 0;
                margin: 0;
                padding: 0;
                max-width: 100%;
                height: auto;
                vertical-align: middle;
                transition: transform 0.3s ease;
                &:hover{
                    transform: scale(1.1);
                }
            }
            }
            
            h1{
                padding-block: 20px;
            }
            p{
                font-style: italic;
            }
        }

    } 
}
    

</style>