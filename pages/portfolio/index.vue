<template>
  <PageWrap>
      <div class="mx-auto max-w-2xl py-8 px-4 sm:py-24 sm:px-6 lg:max-w-7xl lg:px-8">
        <div class="text-center">
          <h2 class="text-3xl font-bold tracking-tight text-white sm:text-4xl">Portfolio</h2>
          <p class="mt-3 max-w-2xl mx-auto text-xl text-white sm:mt-4">
            Here are some of my projects.
          </p>
        </div>
        <div class="mt-12 max-w-lg mx-auto grid gap-5 lg:grid-cols-3 lg:max-w-none">
          <div v-for='work in works' :key='work.id'>
            <div class="flex flex-col rounded-lg shadow-lg overflow-hidden transform transition-all hover:scale-105">
              <div class="flex-shrink-0 bg-white">
                <img class="h-48 w-full object-cover" :src="work.images[0]" alt="">
              </div>
              <div class="flex-1 bg-white p-6 flex flex-col justify-between">
                <div class="flex-1">
                  <p class="text-sm font-medium" style='color: #2a9d8f'>
                    {{ work.category }}
                  </p>
                  <p class="text-xl font-semibold text-gray-900">
                    {{ work.name }}
                  </p>
                  <p class="mt-3 text-base text-gray-500">
                    {{ work.description }}
                  </p>
                  <router-link :to="`/portfolio/work/${work.slug}`">
                    <div class='mt-4 py-2 px-2 border text-center text-white bg-gray-700 border-outline-green rounded-md transition-all hover:bg-gray-200 hover:text-gray-700'>View more</div>
                  </router-link>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
  </PageWrap>

</template>

<script>
import work from '~/mock/work.json';

export default {
  data() {
    return {
      works: work,
    }
  }
}

</script>

<style scoped>
  .vueGreen {
    color: #2a9d8f;
  }
</style>
