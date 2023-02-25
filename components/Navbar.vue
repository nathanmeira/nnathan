<template>
  <header class='bg-white'>
    <div class="mx-auto px-8">
      <div class="flex items-center justify-between py-4 space-x-10">
        <router-link class="text-2xl text-gray-800 no-underline" to="/">nnathan.com</router-link>
        <div class="hidden md:flex md:items-center">
          <router-link class="text-gray-800 no-underline px-3" to="/timeline">Timeline</router-link>
          <router-link class="text-gray-800 no-underline px-3" to="/portfolio">Portfolio</router-link>
        </div>
        <div class="md:hidden">
          <button class="text-gray-800 flex self-center no-underline" @click="showMobileMenu = !showMobileMenu">
            <svg v-if="!showMobileMenu" class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"></path>
            </svg>
            <svg v-else class="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
            </svg>
          </button>
        </div>
      </div>
    </div>
    <transition name="menu-fade">
      <div v-if="showMobileMenu" class="fixed top-16 left-0 h-full bg-white z-40 w-full shadow-2xl overflow-hidden">
        <div class="relative">
          <div class="absolute inset-0 h-full">
            <div class="mt-2 px-8 bg-white h-full">
              <router-link class="block text-xl py-2 text-gray-800 no-underline" to="/timeline">Timeline</router-link>
              <hr>
              <DropdownWorkMenu />
            </div>
          </div>
        </div>
      </div>
    </transition>
  </header>
</template>

<script>
export default {
  data() {
    return {
      showMobileMenu: false
    }
  },
}
</script>

<style>
.menu-fade-enter-active, .menu-fade-leave-active {
  transition: all 0.3s ease-out;
}
.menu-fade-enter {
  opacity: 0;
}
.menu-fade-enter-to {
  opacity: 1;
}
.menu-fade-leave {
  opacity: 1;
}
.menu-fade-leave-to {
  opacity: 0;
}


</style>
