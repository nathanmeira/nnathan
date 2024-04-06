<template>
  <div class="mt-12">
    <h1 class="text-3xl font-bold mb-4">My Timeline</h1>
    <hr class="w-full mt-2 mb-20 border-b-gray">
    <div>
      <ul role="list" class="-mb-8">
        <li v-for="event in timeline" :key="event.index">
          <div class="relative pb-8">
            <span class="absolute left-4 top-4 -ml-px h-full w-0.5 bg-gray-200" aria-hidden="true"></span>
            <div class="relative flex space-x-3">
              <div>
            <span class="h-8 w-8 rounded-full bg-gray-400 flex items-center justify-center ring-8 ring-white">
              <UserIcon />
            </span>
              </div>
              <div class="flex min-w-0 flex-1 justify-between space-x-4 pt-1.5">
                <div>
                  <p class="text-sm text-gray-500">{{ event.title }}</p>
                  <span class="text-xs font-medium rounded-full px-2 py-1 mr-2 mt-2" :class="eventColor(event.type)">{{ event.type }}</span>
                </div>
                <div class="whitespace-nowrap text-right text-sm text-gray-500 font-thin">
                  <time>{{ event.date }}</time>
                </div>
              </div>
            </div>
          </div>
        </li>
      </ul>
    </div>

  </div>
</template>

<script>
import timelineData from '~/assets/mockdata/timeline.json'
import UserIcon from "~/components/icons/UserIcon.vue";
export default {
  components: {UserIcon},
  data() {
    return {
      timeline: timelineData,
    };
  },
  methods: {
    eventColor(event) {
      if (event === 'Life') {
        return 'text-green-600 bg-green-100'
      } else if (event === 'Work') {
        return 'text-blue-600 bg-blue-100'
      } else {
        return 'text-gray-600 bg-gray-100'
      }
    }
  }
};

</script>

<style scoped>

</style>