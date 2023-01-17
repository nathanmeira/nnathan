<template>
  <PageWrap>
    <div class="overflow-hidden rounded-md mt-4 py-4 mx-8">
      <div class="relative mx-auto max-w-xl">
        <div class="text-center">
          <h2 class="text-3xl font-bold tracking-tight text-gray-900 sm:text-4xl">Get in touch</h2>
          <p class="mt-4 text-lg leading-6 text-gray-500">Nullam risus blandit ac aliquam justo ipsum. Quam mauris volutpat massa dictumst amet. Sapien tortor lacus arcu.</p>
        </div>
        <div class="mt-12">
          <form action="#" method="POST" class="grid grid-cols-1 gap-y-6 sm:grid-cols-2 sm:gap-x-8">
            <div class="sm:col-span-2">
              <label for="first-name" class="block text-sm font-medium text-gray-700">Name *</label>
              <div class="mt-1">
                <input type="text" name="name" id="name" autocomplete="given-name" class="block w-full rounded-md border-gray-300 py-3 px-4 shadow-sm focus:border-indigo-500 focus:ring-indigo-500" />
              </div>
            </div>
            <div class="sm:col-span-2">
              <label for="company" class="block text-sm font-medium text-gray-700">Company</label>
              <div class="mt-1">
                <input type="text" name="company" id="company" autocomplete="organization" class="block w-full rounded-md border-gray-300 py-3 px-4 shadow-sm focus:border-indigo-500 focus:ring-indigo-500" />
              </div>
            </div>
            <div class="sm:col-span-2">
              <label for="email" class="block text-sm font-medium text-gray-700">Email *</label>
              <div class="mt-1">
                <input id="email" name="email" type="email" autocomplete="email" class="block w-full rounded-md border-gray-300 py-3 px-4 shadow-sm focus:border-indigo-500 focus:ring-indigo-500" />
              </div>
            </div>
            <div class="sm:col-span-2">
              <label for="message" class="block text-sm font-medium text-gray-700">Message *</label>
              <div class="mt-1">
                <textarea id="message" name="message" rows="4" class="block w-full rounded-md border-gray-300 py-3 px-4 shadow-sm focus:border-indigo-500 focus:ring-indigo-500" />
              </div>
            </div>
            <div class="sm:col-span-2">
              <button type="submit" class="inline-flex w-full items-center justify-center rounded-md border border-transparent bg-gray-800 px-6 py-3 text-base font-medium text-white shadow-sm hover:bg-gray-500 focus:outline-none focus:ring-2 focus:ring-gray-800 focus:ring-offset-2">Let's talk</button>
            </div>
          </form>
        </div>
      </div>
    </div>
  </PageWrap>
</template>

<script>
export default {
}
</script>

<style scoped>

</style>
