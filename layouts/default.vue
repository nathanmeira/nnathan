<template>
  <div class="flex">
    <div id="left" class="hidden md:flex justify-end flex-none w-1/3 h-screen overflow-y-auto border-r">
      <div class="mt-32">
        <Sidebar :menu-items="menuItems" />
      </div>
    </div>

    <div id="right" class="flex-auto bg-white p-10 overflow-y-auto">
      <div class="flex justify-between md:hidden pb-14">
        <div>
          <h1 class="text-xl font-bold">NATHAN M.</h1>
          <hr class="w-10 mt-6 border-[2px] border-gray-800">
        </div>
        <button @click="toggleMobileMenu" class="text-gray-600 focus:outline-none">
          <svg class="h-10 w-10" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16m-7 6h7"></path>
          </svg>
        </button>
      </div>

      <div class="lg:w-3/4 w-full">
        <nuxt-page />
      </div>

    </div>

    <div :class="{ 'block': mobileMenuOpen, 'hidden': !mobileMenuOpen }" class="md:hidden fixed inset-0 bg-white z-50">
      <transition name="fade">
        <div class="flex justify-end p-10">
          <button @click="toggleMobileMenu" class="text-gray-600 focus:outline-none">
            <svg class="h-10 w-10" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
            </svg>
          </button>
        </div>
      </transition>

        <ul class="p-10">
          <nuxt-link v-for="(item, index) in menuItems" :key="item.name" :to="item.link" class="block" @click="toggleMobileMenu">
            <li class="pl-4 pt-4 pb-4 border-t border-t-gray hover:bg-zinc-50 hover:font-bold transition-all" :class="{ 'border-b border-b-gray': index === menuItems.length - 1 }">
              {{ item.name }}
            </li>
          </nuxt-link>
        </ul>

    </div>
  </div>
</template>

<script>
import Navbar from "~/components/Sidebar.vue";

export default {
  components: {Navbar},
  data() {
    return {
      mobileMenuOpen: false,
      menuItems: [
        {name: 'Home', link: '/'},
        {name: 'Portfolio', link: '/portfolio'},
        {name: 'My Timeline', link: '/timeline'},
        {name: 'Contact', link: '/contact'}
      ]
    };
  },
  methods: {
    toggleMobileMenu() {
      this.mobileMenuOpen = !this.mobileMenuOpen;
    }
  }
}
</script>

<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity 0.5s, transform 0.5s;
}

.fade-enter, .fade-leave-to {
  opacity: 0;
  transform: translateY(-20px);
}

@media (min-width: 768px) {
  #left {
    position: fixed;
    left: 0;
    top: 0;
    bottom: 0;
  }

  #right {
    margin-left: 33%;
  }
}
</style>

