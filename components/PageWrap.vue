<template>
  <div class='flex flex-col min-h-screen'>
    <div class='sticky top-0 z-10'>
      <Navbar />
    </div>
    <div class='flex-1'>
      <slot />
    </div>
    <Footer class='w-full' />
  </div>
</template>

<style>
/* Set the footer to always stay at the bottom */
.footer {
  position: sticky;
  bottom: 0;
}
</style>
