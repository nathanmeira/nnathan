
<template>
  <h1 class="text-4xl font-bold">NATHAN M.</h1>
  <hr class="w-14 mt-8 border-[2px] border-gray-800">

  <p class="mt-8 text-base text-gray-600 w-3/5">”Simplicity is the ultimate sophistication” <br> <span class="text-sm text-gray-400">Leonardo Da Vinci</span></p>
  <ul class="mt-10">
    <nuxt-link v-for="(item, index) in menuItems" :key="item.name" :to="item.link" class="block">
      <li class="pl-4 pt-4 pb-4 border-t border-t-gray hover:bg-zinc-50 hover:font-bold transition-all" :class="{ 'border-b border-b-gray': index === menuItems.length - 1 }">
        {{ item.name }}
      </li>
    </nuxt-link>
  </ul>
</template>

<script>
export default {
  name: 'Sidebar',
  props: {
    menuItems: {
      type: Array,
      required: true
    }
  }
};
</script>

<style scoped>

</style>
