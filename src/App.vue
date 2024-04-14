<script>
import  vMainWrapper  from "./components/v-main-wrapper.vue";
export default {
  name:'app',
  components:{
    vMainWrapper
  },
  data() {
    return {

    }
  }
}
</script>

<template>
  <!-- <div class="app">
  </div> -->
  <vMainWrapper />
</template>

<style>
@import 'materialize-css/dist/css/materialize.min.css';
header {
  line-height: 1.5;
  max-height: 100vh;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}



@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }

  
}
</style>