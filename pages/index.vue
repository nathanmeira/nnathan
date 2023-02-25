<template>
  <PageWrap>
    <div class="z-10 mt-20 pb-20 sm:pb-24 xl:pb-0">
      <div class="mx-auto flex max-w-7xl flex-col items-center gap-y-10 gap-x-8 px-6 sm:gap-y-8 lg:px-8 xl:flex-row xl:items-stretch">
        <div class="w-full max-w-2xl xl:-mb-8 xl:w-96 xl:flex-none">
          <div class="relative aspect-[2/1] h-full md:-mx-8 xl:mx-0 xl:aspect-auto">
            <img class="absolute inset-0 h-full w-full rounded-2xl bg-gray-800 object-cover shadow-2xl" src="https://i.imgur.com/pZRKh4A.jpeg" alt="" />
          </div>
        </div>
        <div class="w-full max-w-2xl xl:max-w-none xl:flex-auto xl:py-24 xl:px-16">
          <figure class="relative isolate pt-6 sm:pt-12">
            <blockquote class="text-xl font-semibold leading-8 text-white sm:text-2xl sm:leading-9">
              <h1>
                <p class='text-4xl text-white mb-4'>Hi, I'm Nathan!</p>
                <p class='text-6xl text-white mb-2'>
                  And I'm a
                </p>
                <span class="md:text-8xl text-7xl typed-text vueGreen">{{ typeValue }}</span>
                <span class="blinking-cursor md:text-8xl text-7xl">|</span>
                <span class="cursor" :class="{ typing: typeStatus }">&nbsp;</span>
              </h1>
            </blockquote>
            <figcaption class="mt-20 text-base">
              <a href='/timeline' class="text-medium px-4 py-2 border-white border hover:text-gray-700 hover:bg-white rounded-md text-white">About me</a>
            </figcaption>
          </figure>
        </div>
      </div>
    </div>
  </PageWrap>
</template>

<script>
export default {
  data: () => {
    return {
      typeValue: "",
      typeStatus: false,
      displayTextArray: ["Developer.", "Designer."],
      typingSpeed: 100,
      erasingSpeed: 100,
      newTextDelay: 2000,
      displayTextArrayIndex: 0,
      charIndex: 0,
    };
  },
  props: {},
  created() {
    setTimeout(this.typeText, this.newTextDelay + 200);
  },
  methods: {
    typeText() {
      if (this.charIndex < this.displayTextArray[this.displayTextArrayIndex].length) {
        if (!this.typeStatus) this.typeStatus = true;
        this.typeValue += this.displayTextArray[this.displayTextArrayIndex].charAt(
          this.charIndex
        );
        this.charIndex += 1;
        setTimeout(this.typeText, this.typingSpeed);
      } else {
        this.typeStatus = false;
        setTimeout(this.eraseText, this.newTextDelay);
      }
    },
    eraseText() {
      if (this.charIndex > 0) {
        if (!this.typeStatus) this.typeStatus = true;
        this.typeValue = this.displayTextArray[this.displayTextArrayIndex].substring(
          0,
          this.charIndex - 1
        );
        this.charIndex -= 1;
        setTimeout(this.eraseText, this.erasingSpeed);
      } else {
        this.typeStatus = false;
        this.displayTextArrayIndex += 1;
        if (this.displayTextArrayIndex >= this.displayTextArray.length)
          this.displayTextArrayIndex = 0;
        setTimeout(this.typeText, this.typingSpeed + 1000);
      }
    },
  },
};
</script>

<style scoped>
  .vueGreen {
    color: #42cfae;
  }

  .blinking-cursor {
    color: #2c3e50;
    -webkit-animation: 1s blink step-end infinite;
    -moz-animation: 1s blink step-end infinite;
    -ms-animation: 1s blink step-end infinite;
    -o-animation: 1s blink step-end infinite;
    animation: 1s blink step-end infinite;
  }
  @keyframes blink {
    from,
    to {
      color: transparent;
    }
    50% {
      color: #2a9d8f;
    }
  }
  @-moz-keyframes blink {
    from,
    to {
      color: transparent;
    }
    50% {
      color: #2a9d8f;
    }
  }
  @-webkit-keyframes blink {
    from,
    to {
      color: transparent;
    }
    50% {
      color: #2a9d8f;
    }
  }
  @-ms-keyframes blink {
    from,
    to {
      color: transparent;
    }
    50% {
      color: #2a9d8f;
    }
  }
  @-o-keyframes blink {
    from,
    to {
      color: transparent;
    }
    50% {
      color: #2a9d8f;
    }
  }
</style>
