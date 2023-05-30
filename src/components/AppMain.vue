<script>
import axios from 'axios';
export default {
   name: "AppMain",
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
               console.log(response.data.results.data);
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
   <div class="container">
      <h1>Sono AppMain</h1>
   </div>
</template>

<style lang="scss" scoped>
@use "../styles/general.scss";
</style>
