<script>
export default {
   name: "AppCard",
   props: {
      image: String,
      titolo: String,
      descrizione: String,
   },
   data() {
      return {

      }
   },
   methods: {

   }
}
</script>

<template>
   <div class="card">
      <img :src="image" :alt="titolo" class="card-img-top"/>
      <div class="card-body">
         <h3 class="card-title text-center">{{titolo}}</h3>
         <p class="card-text">{{descrizione}}</p>
         <!-- <a href="#" class="btn btn-primary">Go somewhere</a> -->
      </div>
   </div>
</template>

<style lang="scss" scoped>
@use "../styles/general.scss";
</style>
