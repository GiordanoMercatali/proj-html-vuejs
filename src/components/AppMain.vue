<template>
    <main>
        <!-- JUMBOTRON -->
        <section class="jumbotron">
            <div class="row d-flex">
                <div class="col-6">
                    <div class="rounded-pill">Development</div>
                    <h2>A Complete Developed Toolset</h2>
                    <p>Lorem ipsum, dolor sit amet consectetur adipisicing elit. Voluptatum, nostrum consectetur? Optio voluptates sit dignissimos. Itaque voluptatibus eligendi iste nulla corrupti, reprehenderit quo enim quae tempore nesciunt aspernatur culpa illum!</p>
                    <button class=" rounded me-3">Get Started</button>
                    <button class=" doc-btn rounded">Documentation</button>
                    <p>Current Version: 2.6.0</p>
                </div>
                <div class="col-6">
                    <img src="./images/about.png">
                </div>
            </div>
        </section>

        <hr>
        <!-- SOCIALS -->
        <section class="socials d-flex justify-content-between">
            <img v-for="(social, indexSocial) in socialsList" :key="indexSocial" :src="getSocialImages(indexSocial)">
        </section>

        <!-- FEATURES -->
        <section class="features">
            <h3>Key Features</h3>
            <p>Start working with <span class="text-primary">Landrick</span>. Lorem ipsum dolor sit amet consectetur, adipisicing elit. </p>
            <div class="row">
                <div class="col" v-for="(feature, indexFeature) in features" :key="feature.title">
                    <div class="card p-2">
                        <span class="icon-container rounded"><i :class="features[indexFeature].icon"></i></span>
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
            
            <div class="p-3 text-center border rounded dark-gray-box">
                <div class="row-6 d-flex border rounded gray-box">
                    <div class="col-3 border-dark rounded dark-gray-box">npm</div>
                    <div class="col-3">nuget</div>
                    <div class="col-3">spm</div>
                    <div class="col-3">github</div>
                </div>
                <div class="row-6 d-flex ms-1 mt-1">
                    <p><span>$</span> npm install <span>-g</span> claps.js </p>
                </div>
            </div>
            <ul class="d-flex gap-2">
                <li><i class="fa-regular fa-circle-check"></i>Organize your data</li>
                <li><i class="fa-regular fa-circle-check"></i>Work with any team</li>
            </ul>
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
                    <button class="rounded"> Read More -> </button>
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
                    <div class="card p-2 shadow">
                        <PlanCard :planType="plan.plan_type" :planBest="plan.isBest" :planPrice="plan.price" :planDesc="plan.desc" />
                    </div>
                </div>
            </div>
        </section>

        <!-- GET STARTED -->
        <section class="get-started text-center">
            <h3>Want to be among the first to find out?</h3>
            <p>Start working with <span class="text-primary">Landrick</span>. Lorem ipsum dolor sit amet consectetur, adipisicing elit. </p>
            <div class="wrapper position-relative"><input type="email" placeholder="Email Address" class="ps-3 rounded-pill w-100"> <button class=" rounded-pill position-absolute top-0 end-0">Get Started</button></div>
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

  p, li{
    color: $text-color-5;
  }

  button{
    background-color: $background-color-17;
    color: $text-color-1;
    padding: 0.4rem 0.8rem;
  }

  button.doc-btn{
    background-color: $background-color-1;
    color: $text-color-8;
    border-color: $border-color-7;
  }

  .rounded-pill:not(input, button){
    width: 50%;
    text-align: center;
    padding: 0.1rem;
    color: $text-color-8;
    background-color: $background-color-16;
    border-color: $border-color-6;
  }

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
            width: 10%;
        }
    }

    .features{
            .card{
            height: 10rem;
        }

        .icon-container{
            width: 40px;
            height: 40px;
            display: flex;
            justify-content: center;
            align-items: center;
            padding: 0.1rem;
            color: $text-color-8;
            background-color: $background-color-16;
            border-color: $border-color-6;
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

        .fa-circle-check, span{
            color: $text-color-4;
        }
    }

    .tools-docs{

        

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

    .get-started{
        .wrapper{
           height: 3rem;

            input{
                height: 3rem;
            }

            button{
                height: 3rem;
            }
        }
    }

}
    
</style>