<template>
  <div>
    <div @click="showDropdown = !showDropdown" class="flex items-center cursor-pointer justify-between">
      <button class="block py-2 text-xl text-gray-800 no-underline">
        Portfolio
      </button>
      <svg v-if="!showDropdown" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 9l6 6 6-6"></path>
      </svg>
      <svg v-else class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M18 15l-6-6-6 6"></path>
      </svg>
    </div>
    <transition name="fade">
      <div v-if="showDropdown" class="bg-white block mb-4 ">
        <WorkList />
      </div>
    </transition>
  </div>
</template>



<script>
import WorkList from './WorkList'

export default {
  components: {
    WorkList
  },
  data() {
    return {
      showDropdown: false
    }
  }
}
</script>

<style>
.fade-enter-active, .fade-leave-active {
  transition: all 0.3s ease-out;
}
.fade-enter {
  opacity: 0;
}
.fade-enter-to {
  opacity: 1;
}
.fade-leave {
  opacity: 1;
}
.fade-leave-to {
  opacity: 0;
}

</style>
