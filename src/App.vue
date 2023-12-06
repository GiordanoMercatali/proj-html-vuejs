<template>
  <AppMain />
  <AppFooter />
</template>

<script>
import axios from 'axios';
import AppMain from "./components/AppMain.vue";
import AppFooter from "./components/AppFooter.vue";


export default {
  components: {
    // AppHeader,
    AppMain,
    AppFooter,
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