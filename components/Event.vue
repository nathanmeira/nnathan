<template>
  <div id="event" class="mb-8 flex justify-between items-center w-full"
  :class='alignRight ? "right-timeline" : "flex-row-reverse left-timeline"'
  >
    <div class="order-1 w-5/12"></div>
    <div class="order-1 w-5/12 px-1 py-4"
      :class='alignRight ? "text-left" : "text-right"'
    >
      <p class="mb-3 text-base vueGreen">{{ date }}</p>
      <h4 class="mb-3 font-bold text-lg md:text-2xl">{{ type }}</h4>
      <p class="text-sm md:text-base leading-snug text-gray-50 text-opacity-100">
        {{ description }}
      </p>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      default: 'Event Title',
    },
    date: {
      type: String,
      default: 'Date',
    },
    description: {
      type: String,
      default: 'Description',
    },
    alignRight: {
      type: Boolean,
      default: false,
    },
  }
}
</script>

<style scoped>
.vueGreen {
  color: #2a9d8f;
}
</style>
