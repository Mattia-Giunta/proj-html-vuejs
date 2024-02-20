<script>



export default {
    name: "CardsApp",      
};

</script>

<template>

    <section class="container">

        <div class="container-card">
            <figure>

                <img src="../../Assets/img/h-2-port-img-1.jpg" alt="">
                
                <div class="container-absolute">
                    <h1>All these illustration</h1>
                    <p>illustratio</p>
                </div>

            </figure>
        </div>

        <div class="container-card">
            <figure>
                <img src="../../Assets/img/h-2-port-img-2.jpg" alt="">

                <div class="container-absolute">
                    <h1>All these illustration</h1>
                    <p>illustratio</p>
                </div>
            </figure>
        </div>

        <div class="container-card">
            <figure>
                <img src="../../Assets/img/h-2-port-img-3.jpg" alt="">

                <div class="container-absolute">
                    <h1>All these illustration</h1>
                    <p>illustratio</p>
                </div>
            </figure>
        </div>

        <div class="container-card">
            <figure>
                <img src="../../Assets/img/h-2-port-img-4.jpg" alt="">

                <div class="container-absolute">
                    <h1>All these illustration</h1>
                    <p>illustratio</p>
                </div>
            </figure>
        </div>

        <div class="container-card">
            <figure>
                <img src="../../Assets/img/h-2-port-img-5.jpg" alt="">

                <div class="container-absolute">
                    <h1>All these illustration</h1>
                    <p>illustratio</p>
                </div>
            </figure>
        </div>

        <div class="container-card">
            <figure>
                <img src="../../Assets/img/h-2-port-img-6.jpg" alt="">

                <div class="container-absolute">
                    <h1>All these illustration</h1>
                    <p>illustratio</p>
                </div>
            </figure>
        </div>

    </section>

</template>


<style lang="scss" scoped>
@use "../../styles/partials/variables" as *;
@use "../../styles/partials/mixins" as *;

section{
    display: flex;
    flex-wrap: wrap;

    .container-card{
        flex-basis: calc(100% / 3);
        aspect-ratio: 1;
        figure{
            position: relative;
            overflow: hidden;
            &:hover .container-absolute{
                right: 20%;
                
                }
            .container-absolute{
                position: absolute;
                background-color: white;
                width: 50%;
                height: 15%;
                padding: 20px;
                top: 40%;
                right: 100%;
                transform: translate(-50%, 0);
                transition: right 0.5s ease;
                
            }

            img{
                display: inline-block;
                border: 0;
                margin: 0;
                padding: 0;
                max-width: 100%;
                height: auto;
                vertical-align: middle;
            }
        }
    }
}
</style>