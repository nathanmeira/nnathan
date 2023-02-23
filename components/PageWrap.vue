<template>
  <div class='bg-gradient-to-b from-gray-200 to-gray-100 h-screen'>
    <div class='sticky top-0 z-10'>
      <Navbar />
    </div>
    <slot />
    <Footer class='fixed bottom-0 left-0 w-full' />
  </div>
</template>
