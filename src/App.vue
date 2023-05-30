<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
   name: "App.vue",
   components: {
      AppHeader,
      AppMain,
   },
   data() {
      return {
         
      }
   }
}
</script>

<template>
   <h1 class="container">Sono App.vue</h1>
   <AppHeader />
   <AppMain />
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/variables.scss" as *;
</style>
