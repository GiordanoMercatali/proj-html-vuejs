<template>
  <AppMain />
</template>

<script>
import axios from 'axios';
import AppMain from "./components/AppMain.vue";


export default {
  components: {
    // AppHeader,
    AppMain,
  },
  data(){
    return{
      // store,
    };
  },  
}
</script>

<style lang="scss">
@use "./style/general.scss";
@import "@fortawesome/fontawesome-free/css/all.css";
  
</style>