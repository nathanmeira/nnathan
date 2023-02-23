<template>
  <div>
    <ul>
      <li
        v-for="work in works"
        :key="work.slug"
        class="border-l-4 pl-1 border-gray-300 hover:border-gray-800 mb-2"
      >
        <router-link :to="`/portfolio/work/${work.slug}`">{{ work.name }}</router-link>
      </li>
    </ul>
  </div>
</template>

<script>
import work from '../mock/work.json';

export default {
  data() {
    return {
      works: work
    }
  },
}
</script>
