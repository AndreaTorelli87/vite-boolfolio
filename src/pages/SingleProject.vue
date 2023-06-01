<script>
   import axios from "axios";

   export default {
      name: "SingleProject",
      data() {
         return {
            project: null,
         }
      },
      mounted() {
         const slug = this.$route.params.slug;
         console.log(slug);

         axios.get(`http://localhost:8000/api/project/${slug}`)
         .then(response => {
            this.project = response.data.project;
            console.log(this.project);
         });
      }
   }
</script>

<template>
   <h1>Sono SingleProject</h1>
   <div v-if="project">
      <img :src="project.img" :alt="project.titolo" class="card-img-top"/>
      <div class="card-body">
         <h3 class="card-title">{{project.titolo}}</h3>
         <p class="card-text text-start">{{project.descrizione}}</p>
      </div>
   </div>
</template>