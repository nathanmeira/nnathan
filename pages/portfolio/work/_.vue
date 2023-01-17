<template>
  <PageWrap>
    <div class='flex flex-col items-center justify-center'>
      <h1 class='text-4xl font-bold tracking-tight text-gray-800 sm:text-5xl'>{{ work.name }}</h1>
      <p>{{ work.description }}</p>
      <a :href="work.source" target="_blank">Source Code</a>
      <a :href="work.demo" target="_blank">Demo</a>
      <div class="image-grid">
        <img v-for="image in work.images" :key="image" :src="image" />
      </div>
    </div>
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
};
</script>

<style scoped>
.image-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-gap: 16px;
}
img {
  width: 100%;
}
</style>
