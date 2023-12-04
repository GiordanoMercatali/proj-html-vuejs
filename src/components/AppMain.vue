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

        <!-- FEATURES -->
        <section class="features">
            <h3>Key Features</h3>
            <p>Start working with <span class="text-primary">Landrick</span>. Lorem ipsum dolor sit amet consectetur, adipisicing elit. </p>
            <div class="row">
                <div class="col" v-for="(feature, indexFeature) in features" :key="feature.title">
                    <FeatureCard :featureIcon="feature.icon" :featureTitle="feature.title" :featureText="feature.text" :featureMore="feature.more" />
                </div>
            </div>
        </section>

    </main>
</template>

<script>
// import axios from "axios";
import FeatureCard from "./FeatureCard.vue";
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

            
            features: [
                {
                    icon:  "fa-solid fa-layer-group",
                    title: "Modular" ,
                    text: "lorem ipsum dolor sit amet" ,
                    more: "Read More",
                },
                {
                    icon:  "fa-solid fa-desktop",
                    title: "Responsive" ,
                    text: "lorem ipsum dolor sit amet" ,
                    more: "Read More",
                },
                {
                    icon:  "fa-solid fa-crosshairs",
                    title: "Customizable" ,
                    text: "lorem ipsum dolor sit amet" ,
                    more: "Read More",
                },
                {
                    icon:  "fa-solid fa-maximize",
                    title: "Scalable" ,
                    text: "lorem ipsum dolor sit amet" ,
                    more: "Read More",
                },
            ]
        }
    },

    components: { FeatureCard },

    methods: {
        getSocialImages(index){
            return `/src/components/images/${this.socialsList[index]}.svg`
        },

        getFeatureIcon(index){
            return `fa-solid ${this.features[index].icon}`
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

    .card{
        height: 20rem;
    }
}
    
</style>