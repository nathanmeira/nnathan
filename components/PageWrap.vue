<template>
  <div class='flex flex-col min-h-screen'>
    <div class='sticky top-0 z-10'>
      <Navbar />
    </div>
    <div class='flex-1'>
      <slot />
    </div>
    <Footer />
  </div>
</template>

<style>
</style>
