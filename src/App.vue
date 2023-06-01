<script>
import AppHeader from "./components/AppHeader.vue";

export default {
   name: "App.vue",
   components: {
      AppHeader,
   },
   data() {
      return {
         
      }
   }
}
</script>

<template>
   <div class="container">
      <AppHeader />
      <router-view/>
   </div>
   
</template>

<style lang="scss">
@use "./styles/general.scss" as *;
@use "./styles/variables.scss" as *;
</style>
