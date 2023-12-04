<template>
    <main>
        <!-- JUMBOTRON -->
        <section class="jumbotron">
            <div class="row d-flex">
                <div class="col-6">
                    <div class="border border-primary rounded-pill">Development</div>
                    <h2>A Complete Developed Toolset</h2>
                    <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Voluptatum, nostrum consectetur? Optio voluptates sit dignissimos. Itaque voluptatibus eligendi iste nulla corrupti, reprehenderit quo enim quae tempore nesciunt aspernatur culpa illum!</p>
                    <button class="btn btn-primary bg-primary rounded me-3">Get Started</button>
                    <button class="btn btn-primary bg-light rounded">Documentation</button>
                    <p>Current Version: 2.6.0</p>
                </div>
                <div class="col-6">
                    <img src="./images/about.png">
                </div>
            </div>
        </section>

        <br>
        <!-- SOCIALS -->
        <section class="socials d-flex justify-content-between">
            <img v-for="(social, indexSocial) in socialsList" :key="social.indexSocial" :src="getSocialImages(indexSocial)">
        </section>
    </main>
</template>

<script>
import axios from "axios";
export default {
    data(){
        return{
            socialsList: [
                "amazon",
                "google",
                "lenovo",
                "paypal",
                "shopify",
                "spotify",
            ],
        }
    },

    methods: {
        getSocialImages(index){
            return `/src/components/images/${this.socialsList[index]}.svg`
        }
    }
}
</script>

<style lang="scss" scoped>
@use "../style/general.scss";
@import "@fortawesome/fontawesome-free/css/all.css" ;

main{
  margin: 0 auto;
  width: 60%;

    .jumbotron{
        img{
            width: 80%;
        }
    }

    .socials{
        img{
            width: 6%;
        }
    }
}
    
</style>