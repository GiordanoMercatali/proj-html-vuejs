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
                    <div class="card">
                        <span class="border border-primary background background-primary"><i :class="features[indexFeature].icon"></i></span>
                        <FeatureCard :featureTitle="feature.title" :featureText="feature.text" />
                        <a href="">Read More<i class="fa-solid fa-angle-right"></i></a>
                    </div>
                </div>
            </div>
        </section>

        <!-- QUICKSTART -->
        <section class="quickstart">
            <div class="text-center">
                <p class="text-primary">Quickstart</p>
                <h3>Awesome isn't it? Let's dive in!</h3>
                <p>Start working with <span class="text-primary">Landrick</span>. Lorem ipsum dolor sit amet consectetur, adipisicing elit. </p>
            </div>
            
            <div class="text-center border rounded dark-gray-box">
                <div class="row-6 d-flex border rounded gray-box">
                    <div class="col-3 border-dark rounded dark-gray-box">Ciao</div>
                    <div class="col-3">Ciao</div>
                    <div class="col-3">Ciao</div>
                    <div class="col-3">Ciao</div>
                </div>
                <div class="row-6">
                    Lorem, ipsum dolor sit amet consectetur adipisicing elit. Dolorum, accusamus ex. Delectus esse, ipsa ducimus ad eius consequatur! Dolores consequuntur commodi iste molestiae eos facere qui amet aut modi voluptate!
                </div>
            </div>
        </section>

        <!-- TOOLS AND DOCS -->
        <section class="tools-docs">
            <div class="row">
                <div class="col-6">
                    <h3>Build tools and extensive documentation</h3>
                    <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ducimus, perspiciatis! Facere ea dolores exercitationem omnis illum dicta. Totam possimus recusandae ad ea incidunt, iure, nam dolor, necessitatibus aspernatur id repellendus!</p>
                    <ul>
                        <li v-for="(tool, indexTool) in tools" :key="indexTool"><i class="fa-regular fa-circle-check"></i> {{ tool }}</li>
                    </ul>
                </div>
                <div class="col-6">
                    <img src="./images/1.png">
                </div>
            </div>
        </section>

        <!-- PLANS (RATES) -->
        <section class="plans">
            <h3>Our rates for developer from landrick team</h3>
            <p>Start working with <span class="text-primary">Landrick</span>. Lorem ipsum dolor sit amet consectetur, adipisicing elit. </p>
            <div class="row">
                <div class="col" v-for="(plan, indexPlan) in plans" :key="plan.title">
                    <div class="card">
                        <PlanCard :planType="plan.plan_type" :planBest="plan.isBest" :planPrice="plan.price" :planDesc="plan.desc" />
                    </div>
                </div>
            </div>
        </section>

    </main>
</template>

<script>
// import axios from "axios";
import FeatureCard from "./FeatureCard.vue";
import PlanCard from "./PlanCard.vue";
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
                    
                },
                {
                    icon:  "fa-solid fa-desktop",
                    title: "Responsive" ,
                    text: "lorem ipsum dolor sit amet" ,
                    
                },
                {
                    icon:  "fa-solid fa-crosshairs",
                    title: "Customizable" ,
                    text: "lorem ipsum dolor sit amet" ,
                    
                },
                {
                    icon:  "fa-solid fa-maximize",
                    title: "Scalable" ,
                    text: "lorem ipsum dolor sit amet" ,
                    
                },
            ],

            tools: [
                "Digital Marketing Solutions for Tomorrow",
                "Our Talented & Experienced Marketing Agency",
                "Create your own skin to match your brand",
            ],

            plans: [
                {
                    plan_type: "Basic",
                    isBest: false,
                    price: "$9.00",
                    desc: "Lorem ipsum dolor sit amet.",
                },
                {
                    plan_type: "Business",
                    isBest: true,
                    price: "$39.00",
                    desc: "Lorem ipsum dolor sit amet.",
                },
                {
                    plan_type: "Enterprise",
                    isBest: false,
                    price: "$79.00",
                    desc: "Lorem ipsum dolor sit amet.",
                },
            ]
        }
    },

    components: { FeatureCard, PlanCard },

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

<style lang="scss">
@use "../style/partials/variables" as *;
@import "@fortawesome/fontawesome-free/css/all.css" ;

main{
  margin: 0 auto;
  width: 60%;

  section{
    margin: 4rem 0;
  }

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

    .features{
        .card{
        height: 10rem;
    }
    }

    .quickstart{
        .dark-gray-box{
            background-color: $background-color-18;
            border-color: $border-color-8;
            color: $text-color-1;
        }

        .gray-box{
            background-color: $border-color-4;
            border-color: $border-color-4;
            }
    }

    .tools-docs{

        color: $text-color-5;

        h3{
            color: $text-color-11;
        }

        img{
            max-width: 60%;
        }

        ul{
            list-style-type: none;
            .fa-circle-check{
                color: $text-color-8;
            }
        }
    }

    .plans{

        h4{
            color: $text-color-11;
        }

        .card{
            color: $text-color-5;

            .fa-circle-check{
                color: $text-color-8;
            }
        }

        .orange-box{
            rotate: 30deg;
            background-color: $background-color-9;
            color: $text-color-1;
        }
    
    }

}
    
</style>