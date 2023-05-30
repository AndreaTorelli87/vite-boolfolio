<script>
import axios from 'axios';
import AppCard from "./AppCard.vue";
export default {
   name: "AppMain",
   components: {
      AppCard
   },
   data() {
      return {
         projects: [],
         contentMaxLength: 200,
         baseUrl: 'http://127.0.0.1:8000',
         currentPage: 1,
         lastPage: null
      }
   },
   methods: {
      getProjects(actualPage) {
         axios.get(`${this.baseUrl}/api/projects`,
            {
               params: {
                  page: actualPage
               }
            }
         )
            .then(response => {
               this.projects = response.data.results.data;
               this.currentPage = response.data.results.current_page;
               this.lastPage = response.data.results.last_page;
            });
      },
   },
   mounted() {
      this.getProjects(1);
   }
}
</script>

<template>
   <div class="container text-center">
      <h1 class="py-3 display-2 fw-bold">Lista dei progetti</h1>
      <nav class="d-flex justify-content-center">
         <ul class="pagination">
            <li class="page-item" @click="getProjects(currentPage - 1)" :class="{'disabled' : currentPage == 1}"><a class="page-link">Previous</a></li>
            <li class="page-item" @click="getProjects(currentPage = page)" v-for="page in lastPage"><a class="page-link">{{ page }}</a></li>
            <li class="page-item" @click="getProjects(currentPage + 1)" :class="{'disabled' : currentPage == lastPage}"><a class="page-link">Next</a></li>
         </ul>
      </nav>
      <div class="row py-5">
         <div class="col-6" v-for="project in projects">
            <AppCard 
               :image="project.img"
               :titolo="project.titolo"
               :descrizione="project.descrizione"
            />
         </div>
      </div>
   </div>
</template>

<style lang="scss" scoped>
@use "../styles/general.scss";
</style>
