<template>
  <PageWrap>
    <section>
      <div class="text-white py-8">
        <div class="container mx-auto flex flex-col items-start md:flex-row my-12 md:my-24">
          <div class="flex flex-col w-full sticky md:top-36 lg:w-1/3 mt-2 md:mt-12 px-8">
            <p class="text-yellow-300 uppercase tracking-loose vueGreen">Timeline</p>
            <p class="text-3xl md:text-4xl leading-normal md:leading-relaxed mb-2">Nathan Meira</p>
            <p class="text-sm md:text-base text-gray-50 mb-4">
              This is my timeline. Check my collection of academic & professional events as well as some experiences along the way.
            </p>
          </div>
          <div id="timeline" class="ml-0 md:ml-12 lg:w-2/3 sticky">
            <div class="container mx-auto w-full h-full">
              <div class="relative wrap overflow-hidden p-10 h-full">
                <div class="border-2-2 border-yellow-555 absolute h-full border vueGreen"
                     style="right: 50%; border: 2px solid; border-radius: 1%;"></div>
                <div class="border-2-2 border-yellow-555 absolute h-full border vueGreen"
                     style="left: 50%; border: 2px solid; border-radius: 1%;"></div>
                <div v-for='(event, index) in events' :key='event.id'>
                  <Event
                    :date="event.date"
                    :type="event.type"
                    :description="event.event"
                    :align-right="isAligned(index-1)"
                  />
                </div>
              </div>
              <img class="mx-auto -mt-36 md:-mt-36" src="https://user-images.githubusercontent.com/54521023/116968861-ef21a000-acd2-11eb-95ac-a34b5b490265.png" />
            </div>
          </div>
        </div>
      </div>
    </section>
  </PageWrap>

</template>

<script>
import timeline from '~/mock/timeline.json';
export default {
  data() {
    return {
      events: timeline,
    }
  },
  computed: {
    isAligned() {
      return function(index) {
        return index % 2 === 0;
      };
    }
  }

}
</script>

<style scoped>
  .vueGreen {
    color: #2a9d8f;
  }
</style>
