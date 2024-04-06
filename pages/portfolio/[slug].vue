<template>
  <div v-if="project" class="mt-12">
    <img class="w-full h-96 object-contain mb-20 rounded-md" :src="project.thumbnail" />
    <h1 class="text-3xl font-bold mb-4">{{ project.name }}</h1>
    <hr class="w-full mt-2 mb-8 border-b-gray">
    <p> {{ project.description }} </p>
    <p v-if="project.url" class="mt-8 text-sm">URL: <a class="text-blue-400" :href="project.url" target="_blank">{{ project.url }}</a></p>
    <img class="object-cover w-full mt-8" :src="project.preview" />
  </div>
  <div v-else class="mt-12">
    <h1 class="text-3xl font-bold mb-4">Not found</h1>
  </div>
</template>

<script>
import { ref, onMounted } from 'vue'
import { useRoute } from 'vue-router'
import projectsData from '~/assets/mockdata/projects.json';

export default {
  setup() {
    const route = useRoute()
    const slug = ref(route.params.slug)
    const project = ref(null)
    const loading = ref(true)

    onMounted(() => {
      const foundProject = projectsData.find(p => p.slug === slug.value);
      if (foundProject) {
        project.value = foundProject;
        loading.value = false
      } else {
        loading.value = false
      }
    });

    return {project, loading}
  }
}
</script>
