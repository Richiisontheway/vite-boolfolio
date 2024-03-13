<script>
import axios from "axios";
export default {
    data() {
        return {
        projects: [],
        };
    },
    created() {
        axios.get("http://127.0.0.1:8000/api/projects").then((res) => {
        console.log(res.data);
        this.projects = res.data.result.data;
        });
    },
};
</script>

<template>
    <main>
        <div>
            <div v-for="project in projects" :key="projects.id">
                <ul>
                    {{ project.title }}
                </ul>
            </div>
        </div>
    </main>
</template>

<style scoped>
main {
  color: red;
}
</style>
