<template>
  <div>
    <Minimo v-show="true" />
    <CardDivider v-show="true" class="mx-auto" />
    <below-divider v-show="true" />
    <Footer v-show="true" />
    
  </div>
</template>

<script>
import Minimo from "./components/Minimo";
import CardDivider from "./components/CardDivider";
import BelowDivider from "./components/BelowDivider.vue";
import Footer from "./components/Footer.vue";

export default {
  name: "App",

  components: {
    Minimo,
    CardDivider,
    BelowDivider,
    Footer,
  },

  data: () => ({
    //
  }),
};
</script>
<style>

</style>
