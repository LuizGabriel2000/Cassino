<template>
  <HomeCassinoVue/>
</template>

<script>
import HomeCassinoVue from './views/HomeCassino.vue';

export default {
  name: 'App',

  components: {
   HomeCassinoVue,
  },

  data: () => ({
    //
  }),
};
</script>

<style>
body {
  position: absolute;
  top: 0;
  left: 0;
  bottom: 0;
  right: 0;
}
</style>
