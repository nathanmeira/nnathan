<template>
  <div class="mt-12">
    <h1 class="text-3xl font-bold mb-4">Portfolio</h1>
    <hr class="w-full mt-2 border-b-gray">
    <ul role="list" class="mx-auto mt-20 grid grid-cols-1 gap-x-8 gap-y-16 sm:grid-cols-2 lg:mx-0 lg:max-w-none lg:grid-cols-3">
      <li v-for="project in projects" :key="project.id">
        <nuxt-link :to="`/portfolio/${project.slug}`">
          <img class="aspect-[3/2] w-full rounded-2xl object-contain p-2 border-2" :src="project.thumbnail" alt="" />
          <h3 class="mt-6 text-lg font-semibold leading-8 tracking-tight text-gray-900">{{ project.name }}</h3>
          <p class="text-base leading-7 text-gray-600 line-clamp-3">{{ project.description }}</p>
          <a class="text-sm text-gray-950">Read more...</a>
        </nuxt-link>
        <ul class="mt-4 flex flex-wrap">
          <li v-for="tag in project.tags" :key="tag" class="text-xs font-medium text-blue-600 bg-blue-100 rounded-full px-2 py-1 mr-2 mt-2">{{ tag }}</li>
        </ul>
      </li>
    </ul>
  </div>
</template>

<script>
import projectsData from '~/assets/mockdata/projects.json';
export default {
  data() {
    return {
      projects: projectsData,
    };
  },
};

</script>

<style scoped>

</style>
