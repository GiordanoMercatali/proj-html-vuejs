<template>
        
            <!-- <i :class="{featureIcon}"> </i> -->
            <h5>{{ featureTitle }}</h5>
            <p>{{ featureText }}</p>
            <a href="">{{ featureMore }}</a>
        
</template>

<script>
export default {
    props:{
        featureIcon: String,
        featureTitle: String,
        featureText: String,
        featureMore: String,
    },
}
</script>

<style lang="scss">

</style>