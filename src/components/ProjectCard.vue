<script>
export default {
  data() {
    return {
      projects: [],
    };
  },
  props: {
    project: Object,
  },
};
</script>

<template>
    <div class="card-container">
        <div class="info-container">
        <div>
            <h3>
                Titolo:
            </h3>
            <h1>
            {{ project.title }}
            </h1>
        </div>
        <span>
            <h3>
                Descrizione:
            </h3>
            {{ project.description }}
        </span>
        <div>
            <img :src="project.image" :alt="project.title" />
        </div>
        <div>
            <h3>
                Type:
            </h3>
            {{ project.type.title }}
        </div>
        <h3>
            Technologies:
        </h3>
        <div v-for="elem in project.technologies">
            {{ elem.title }}
        </div>
        <span>
            <h3>
                Data:
            </h3>
            {{ project.date }}
        </span>
        </div>
    </div>
</template>

<style scoped>
.card-container {
    display: flex;
    width: 300px;
}
</style>
