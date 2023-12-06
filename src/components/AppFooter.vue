<template>
    <footer>
        <!-- UPPER FOOTER -->
        <div class="upper-footer">
            <div class="row">
                <div class="col">
                    <img src="./images/logo-light.png">
                    <p>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Asperiores, nulla fugiat!</p>
                    <div class="d-flex gap-2">
                        <div v-for="(icon, indexIcon) in socialIcons" :key="indexIcon">
                            <i :class="socialIcons[indexIcon]"></i>                        
                        </div>
                    </div>
                </div>
                <div v-for="(item, indexItem) in footerItems" :key="footerItems" class="col">
                    <FooterItem :footTitle="item.title" :footList="item.list" /></div>
                
                    <div class="col">
                        <h4>Newsletter</h4>
                        <p>Sign up</p>
                        <div class="form">
                            <p>Write</p>
                            <div class="wrapper position-relative">
                                <input type="email" class="rounded mb-4" placeholder="Your email here:">
                                <i class="fa-regular fa-envelope"></i>
                            </div>
                            <br>
                            <button class="rounded px-5 py-2">Subscribe</button>
                        </div>
                    </div>
                
                </div>
                
        </div>
        
        <!-- LOWER FOOTER -->
        <div class="lower-footer position-relative w-100 border-top">
            <div class="row d-flex justify-content-between">
                <div class="col">
                    <p class="made-by">Made with <span>&hearts;</span> by landrick team</p>
                </div>
                <div class="col">
                    <ul class="d-flex gap-1">
                        <li v-for="(card, indexCard) in creditCards" :key="indexCard"><img :src="getCreditImages(indexCard)"></li>
                    </ul>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
import FooterItem from "./FooterItem.vue";

export default {
    data(){
        return{
            
            socialIcons: [
                "fa-brands fa-facebook-f",
                "fa-brands fa-instagram",
                "fa-brands fa-twitter",
                "fa-brands fa-linkedin-in",
            ],
            
            footerItems: [
                {
                    title: "Company",
                    list: [
                        "About us",
                        "Services",
                        "Team",
                        "Pricing",
                        "Project",
                        "Careers",
                        "Blog",
                        "Login",
                    ],
                },

                {
                    title: "Useful Links",
                    list: [
                        "Terms of Services",
                        "Privacy Policy",
                        "Documentation",
                        "Changelog",
                        "Components",
                    ],
                },
            ],

            creditCards: [
                "american-ex",
                "discover",
                "master-card",
                "paypal",
                "visa",
            ],
        }
    },

    components: { FooterItem },

    methods: {
        getCreditImages(index){
            return `/src/components/images/${this.creditCards[index]}.png`
        },

        getSocialIcon(index){
            return `fa-brands ${this.socialIcons[index]}`
        },
    }
    
}
</script>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@import "@fortawesome/fontawesome-free/css/all.css" ;

footer{

    padding: 0 10rem;

    .upper-footer{
        .col{
            max-width: 25%;
            color: $text-color-1;

            ul{
                li{
                    p{
                        color: $text-color-5;
                    }
                }
            }

            img{
                width: 50%;
            }
        }

        p{
            color: $text-color-5;
        }

        .wrapper{

            color: $text-color-5;

            input{
                background-color: $background-color-19;
                padding: .5rem 0 .5rem 1.5rem;
            }

            i{
                position: absolute;
                top: 1rem;
                left: 3px;
            }
        }

        button{
            font-weight: bold;
            color: $text-color-8;
            background-color: $background-color-19;
        }
    }

    background-color: $background-color-20;
    .lower-footer{
        display: flex;
        justify-content: center;

            .row{
                gap: 50rem;
            }

            li{
                list-style-type: none;
            }
    }

    p.made-by{
        color: $text-color-1;
        
        span{
            color: $text-color-7;
        }
    }
}
    
</style>