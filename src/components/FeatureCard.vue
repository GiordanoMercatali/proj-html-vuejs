<template>
    <h5>{{ featureTitle }}</h5>
    <p>{{ featureText }}</p>
</template>

<script>
export default {
    props:{        
        featureTitle: String,
        featureText: String,
    },
}
</script>

<style lang="scss">

</style>