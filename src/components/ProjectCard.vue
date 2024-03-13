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
        Titolo:
        <h1>
          {{ project.title }}
        </h1>
      </div>
      <span>
        {{ project.description }}
      </span>
      <div>
        <img :src="project.image" :alt="project.title" />
      </div>
      <div>
        {{ project.type.title }}
      </div>
      <div v-for="elem in project.technologies">
        {{ elem.title }}
      </div>
      <span>
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
