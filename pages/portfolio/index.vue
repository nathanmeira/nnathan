<template>
  <div class="mt-12">
    <h1 class="text-3xl font-bold mb-4">Portfolio</h1>
    <hr class="w-full mt-2 border-b-gray">
    <ul role="list" class="mx-auto mt-20 grid grid-cols-1 gap-x-8 gap-y-16 sm:grid-cols-2 lg:mx-0 lg:max-w-none lg:grid-cols-3">
      <li v-for="project in projects" :key="project.name">
        <nuxt-link :to="`/portfolio/${project.link}`">
          <img class="aspect-[3/2] w-full rounded-2xl object-cover" :src="project.thumbnail" alt="" />
          <h3 class="mt-6 text-lg font-semibold leading-8 tracking-tight text-gray-900">{{ project.name }}</h3>
          <p class="text-base leading-7 text-gray-600">{{ project.description }}</p>
        </nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      projects: [
        {
          name: 'CIBC Capital Markets',
          description: 'CIBC Capital Markets Website',
          thumbnail: 'https://upload.wikimedia.org/wikipedia/commons/6/66/CIBC_CM.png',
          tags: ['Finance', 'Banking', 'Investment'],
          link: 'cibc-capital-markets',
        },
        {
          name: 'S&P Global Sustainable1',
          description: 'S&P Global Sustainable1 pages',
          thumbnail: '',
          tags: ['Finance', 'Banking', 'Investment'],
          link: 'spglobal-sustainable1',
        },
        {
          name: 'S&P Market Intelligence',
          description: 'S&P Market Intelligence pages',
          thumbnail: '',
          tags: ['Finance', 'Banking', 'Investment'],
          link: 'spglobal-market-intelligence',
        },
        {
          name: 'SIDExchange',
          description: 'SIDExchange Website',
          thumbnail: '',
          tags: ['Finance', 'Banking', 'Investment'],
          link: 'sidexchange',
        },
        {
          name: 'SIDExchange',
          description: 'SIDE INTEGRATE system',
          thumbnail: '',
          tags: ['Finance', 'Banking', 'Investment'],
          link: 'sidexchange',
        },
      ],
    };
  },
};

</script>

<style scoped>

</style>
