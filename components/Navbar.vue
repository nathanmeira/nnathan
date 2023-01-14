<template>
  <header class="bg-gray-800">
    <div class="mx-auto px-6">
      <div class="flex items-center justify-between py-4 space-x-10">
        <router-link class="text-2xl text-gray-300 no-underline" to="/">nnathan.com</router-link>
        <div class="hidden md:flex md:items-center">
          <router-link class="text-gray-300 no-underline px-3" to="/work">My Work</router-link>
          <router-link class="text-gray-300 no-underline px-3" to="/contact">Contact</router-link>
        </div>
        <div class="md:hidden">
          <button class="text-gray-500 flex self-center no-underline" @click="showMobileMenu = !showMobileMenu">
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
    <header class="bg-white shadow">
      <div class="mx-auto py-6 px-6">
        <h1 class="text-xl font-bold tracking-tight text-gray-900"> {{ routeName }} </h1>
      </div>
    </header>
    <transition name="menu-slide">
      <div v-if="showMobileMenu" class="fixed h-full bg-white z-40 w-3/5 shadow-2xl">
        <div class="relative">
          <div class="absolute inset-0 h-full">
            <div class="bg-white h-full">
              <router-link class="block py-2 px-4 text-gray-800 no-underline" to="/">Home</router-link>
              <hr>
              <router-link class="block py-2 px-4 text-gray-800 no-underline" to="/work">My Work</router-link>
              <hr>
              <router-link class="block py-2 px-4 text-gray-800 no-underline" to="/contact">Contact</router-link>
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
  computed: {
    routeName() {
      const route = this.$route.name
      if (route === '/' || route === 'index') {
        return 'Home'
      }
      if (route === 'work') {
        return 'My Work'
      }
      else {
        return this.$route.name.charAt(0).toUpperCase() + this.$route.name.slice(1)
      }
    }
  }
}
</script>

<style>
.menu-slide-enter-active, .menu-slide-leave-active {
  transition: all 0.3s ease-out;
}
.menu-slide-enter {
  transform: translateX(-100%);
}
.menu-slide-enter-to {
  transform: translateX(0);
}
.menu-slide-leave {
  transform: translateX(0);
}
.menu-slide-leave-to {
  transform: translateX(-100%);
}

hr {
  @apply mx-2;
}
</style>
