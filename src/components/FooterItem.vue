<template>
    <h4>{{ footTitle }}</h4>
    <ul>
        <li v-for="(elem, elemIndex) in footList"> <p><i class="fa-solid fa-angle-right"></i> {{ footList[elemIndex] }}</p> </li>
    </ul>
</template>

<script>
export default {
    props:{
        footTitle: String,
        footList: Array,
    },
}
</script>

<style lang="scss">
    
</style>