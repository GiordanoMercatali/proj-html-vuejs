<template>
    <div class="position-relative">
        <div class="rounded-pill">{{ planType }}</div>
        <div v-if="planBest" class="position-absolute top-0 end-0 orange-box">Best</div>
        <h4>{{ planPrice }}</h4>
        <p>Per Month</p>
        <p>{{ planDesc }}</p>
        <br>
        <ul>
            <li v-for="(perk, indexPerk) in perks" :key="indexPerk"> <i class="fa-regular fa-circle-check"></i> {{ perk }} </li>
        </ul>
        <button class="rounded w-100">Buy Now</button>
        <p>*No credit card required</p>
    </div>
</template>

<script>
export default {
    props:{
        planType: String,
        planBest: Boolean,
        planPrice: String,
        planDesc: String,
    },

    data(){
        return{
            perks: [
                "Full Access",
                "Enhanced Security",
                "Source Files",
                "1 Domain Free",
                "Enhanced Security",
            ]
        }
    }
}
</script>

<style lang="scss">
    li{
        list-style-type: none;
    }

</style>