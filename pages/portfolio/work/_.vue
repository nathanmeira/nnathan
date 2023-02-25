<template>
  <PageWrap>
    <section class="relative h-screen">
      <div class="aspect-w-3 aspect-h-2 overflow-hidden sm:aspect-w-5 lg:aspect-none lg:h-full lg:absolute lg:h-full lg:w-1/2 lg:pr-4 xl:pr-16">
        <img :src="work.images[0]" class="h-full w-full object-cover object-center lg:h-full lg:w-full" />
      </div>

      <div class="mx-auto max-w-2xl px-4 pt-4 md:pt-16 pb-24 sm:px-6 sm:pb-32 lg:grid lg:max-w-7xl lg:grid-cols-2 lg:gap-x-8 lg:px-8 lg:pt-32">
        <div class="lg:col-start-2 text-white">
          <a class='text-white transition-all hover:text-gray-200' href='/portfolio'>
            <span>
              <svg class="h-5 w-5 mb-2 inline-block transform rotate-90" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 20 20" fill="currentColor" aria-hidden="true">
                <path fill-rule="evenodd" d="M7.293 7.293a1 1 0 011.414 0L12 10.586l3.293-3.293a1 1 0 111.414 1.414l-4 4a1 1 0 01-1.414 0l-4-4a1 1 0 010-1.414z" clip-rule="evenodd" />
              </svg>
              Return to Portfolio
            </span>
          </a>
          <p class="mt-4 mb-4 text-4xl font-bold tracking-tight vueGreen">{{ work.name }}</p>
          <p class="mb-4">{{ work.description }}</p>
          <div class='grid md:grid-cols-2 gap-4 grid-cols-1 text-center'>
            <a :href='work.demo' class="px-2 py-4 border-2 rounded-md transition-all hover:bg-white hover:text-black"> View Demo</a>
            <a :href='work.source' class="px-2 py-4 border-2 rounded-md transition-all hover:bg-white hover:text-black">View Source</a>
          </div>

          <div class="flex overflow-x-auto mt-6">
            <span v-for="item in work.stack" :key="item.id" class="rounded-full border-3 bg-white py-1 px-3 mr-2">
              <div class="text-sm font-medium text-gray-700">{{ item }}</div>
            </span>
          </div>
        </div>
      </div>
    </section>
  </PageWrap>
</template>

<script>
  import work from '~/mock/work.json';

  export default {
    // eslint-disable-next-line require-await
    async asyncData({ route, error }) {
      const slug = route.path.replace(/^\/|\/$/g, '').split("/").pop();
      const workData = work.find(w => w.slug === slug);
      if (!workData) {
        return error({ statusCode: 404 });
      }
      return { work: workData };
    },
    data() {
      return {
        work: {},
        features: [
          {
            name: 'Durable',
            description: 'The leather cover and machined steel disc binding stand up to daily use for years to come.',
          },
          {
            name: 'Refillable',
            description: 'Buy it once and refill as often as you need. Subscribe and save on routine refills.',
          },
          {
            name: 'Thoughtfully designed',
            description:
              'The comfortable disc binding allows you to quickly rearrange pages or combine lined, graph, and blank refills.',
          },
          { name: 'Locally made', description: 'Responsibly and sustainably made real close to wherever you are, somehow.' },
        ],
      };
    },
  };
</script>

<style scoped>

.vueGreen {
  color: #2a9d8f;
}

</style>


=========
