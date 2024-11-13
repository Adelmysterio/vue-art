<script>
import AppMain from './components/AppMain.vue';
export default {
  data() {
    return {

    }
  },
  components: {
    AppMain
  }
}
</script>

<template>
  <main>
    <AppMain />
  </main>
</template>

<style lang=scss>
@use './assets/styles/general.scss';
@use './assets/styles/partials/variables' as *;
/* @use '../node_modules/bootstrap/scss/bootstrap.scss'; */
</style>