<script>
export default {
   name: "AppCard",
   props: {
      image: String,
      titolo: String,
      descrizione: String,
      slug: String,
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
         <h3 class="card-title">{{titolo}}</h3>
         <p class="card-text text-start">{{descrizione}}</p>
         <router-link :to="{name:'single-project', params: {slug}}" class="btn btn-succes">
            <i class="fa-solid fa-eye"></i>
         </router-link>
      </div>
   </div>
</template>

<style lang="scss" scoped>
@use "../styles/general.scss";
</style>
