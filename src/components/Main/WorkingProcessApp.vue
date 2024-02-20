<script>



export default {
    name: "WorkingProcessApp",      
};

</script>

<template>

    <section>

        <div>
            <h1>Working </h1>
            <span>process</span>
        </div>

        <div class="card-container">

            <figure>
                
                <div>
                    <i class="fa-solid fa-lightbulb"></i>
                </div>
                
                <h3>First there an idea</h3>
                <p>Lorem ipsum dolor sit, conetu adipisc sed be et ore aliqua pleasure itself.</p>
            </figure>

            <figure>
                
                <div>
                    <i class="fa-regular fa-comment"></i>
                </div>
                
                <h3>Then we talk about</h3>
                <p>Lorem ipsum dolor sit, conetu adipisc sed be et ore aliqua pleasure itself.</p>
            </figure>

            <figure>

                <div>
                    <i class="fa-solid fa-cloud"></i>
                </div>
                
                <h3>And we think about</h3>
                <p>Lorem ipsum dolor sit, conetu adipisc sed be et ore aliqua pleasure itself.</p>
            </figure>

            <figure>
                
                <div>
                    <i class="fa-solid fa-pen-clip"></i>
                </div>
                
                <h3>So we draw along</h3>
                <p>Lorem ipsum dolor sit, conetu adipisc sed be et ore aliqua pleasure itself.</p>
            </figure>

        </div>


    </section>



</template>


<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

section{
    padding-block: 100px;
    
    div{
        text-align: center;
       
        h1{
        
            font-weight: 300;
            font-size: 70px;
            display: inline;
        
        }
        span{
            font-size: 70px;
            font-family: "Playfair Display", serif;
            font-optical-sizing: auto;
            font-weight: 500;
            font-style: normal;
            
        }
    }

    .card-container{
        
        width: 70%;
        margin: 0 auto;
        background-image: url(../../Assets/svg/svg-3.svg);
        background-repeat: no-repeat;
        background-position: center;
        display: flex;
        padding-top: 70px;
        
        
        figure{
            
            flex-basis: calc(100% / 4);
            padding: 20px 10px;
            div{
                
                
                i{
                    margin-bottom: 30px;
                    font-size: 50px;
                    border-radius: 50%;
                    padding: 60px;
                    aspect-ratio: 1;
                    background-color: #FAF7F1;
                }
            }
        }
    }
}
.fa-lightbulb{
    color: #BADAC9;
}
.fa-comment{
    color: #F8D12D;
}
.fa-cloud{
    color: #80465F;
}
.fa-pen-clip{
    color: #EB6950;
}

</style>