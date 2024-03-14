<script>
import ProjectCard from "./ProjectCard.vue";
import axios from "axios";
export default {
  data() {
    return {
      projects: [],
      currentPage: 1,
      lastPage: 1,
    };
  },
  mounted() {
    this.getProjects(this.currentPage);
  },
  methods: {
    getProjects(page) {
      axios
        .get("http://127.0.0.1:8000/api/projects", {
          params: {
            page: page,
          },
        })
        .then((res) => {
          console.log(res.data);
          this.projects = res.data.result.data;
          this.currentPage = res.data.result.current_page;
          this.lastPage = res.data.result.last_page;
        });
    },
    prevPage() {
        console.log(this.currentPage)
        if (this.currentPage > 1) {
            this.getProjects(this.currentPage - 1);
        }
    },
    nextPage() {
        console.log(this.currentPage)
        if (this.currentPage < this.lastPage) {
            this.getProjects(this.currentPage + 1);
        }
    },
    
  },
  components: {
    ProjectCard,
  },
};
</script>

<template>
    <main>
        <div class="container">
            <ProjectCard
                v-for="project in projects"
                :key="projects.id"
                :project="project"
            />
        </div>
        <div class="nav_container">
            <button @click="prevPage">Precedente</button>
            <button @click="nextPage">Successivo</button>
        </div>
    </main>
</template>

<style scoped>
.container {
  display: flex;
  justify-content: space-around;
}
.nav_container{
    display: flex;
    justify-content: space-around;
    margin-top: 20px;
}
button{
    background-color: blue;
    border-radius: 20px;
    padding: 5px;
    color: white;
}
</style>
