<template>
  <footer class="bg-transparent py-4">
    <div class="container mx-auto text-center text-gray-300">
      nnathan.com - Copyright © {{currentYear}}
    </div>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      currentYear: new Date().getFullYear()
    }
  }
}
</script>

<style>
footer{
  position: relative;
  bottom: 0;
  left: 0;
  right: 0;
}
</style>
