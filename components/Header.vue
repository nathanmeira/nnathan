<template>
  <section id="header" class="overflow-hidden">
    <div class="mx-auto">
      <div id="left-side" class="side">
        <h2 class="title">
          <p>Hey, I'm <b>Nathan</b>!</p>
          and I'm a <span class="terminal">Developer</span>
        </h2>
      </div>
      <div id="right-side" class="side">
        <h2 class="title">
          <p>Hey, I'm <b>Nathan</b>!</p>
          and I'm a <span class="fancy">Designer</span>
        </h2>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  mounted() {
    this.handleIntro();
  },
  methods: {
    handleIntro() {
      const left = document.getElementById("left-side");

      const handleMove = e => {
        left.style.width = `${e.clientX / window.innerWidth * 100}%`;
      }

      document.onmousemove = e => handleMove(e);

      document.ontouchmove = e => handleMove(e.touches[0]);
    }
  }
}
</script>

<style>
:root {
  --dark: rgb(20, 20, 20);

  --vue: rgb(42, 157, 143);

  --left-color: var(--dark);
  --right-color: var(--vue);
}

body {
  background-color: var(--dark);
  margin: 0px;
}

.side {
  display: grid;
  height: 100vh;
  overflow: hidden;
  place-items: center;
  position: absolute;
  width: 100%;
}

.side .title {
  font-family: "Rubik", sans-serif;
  font-size: 8vw;
  margin: 0px 10vw;
  width: 80vw;
}

.side .fancy {
  font-family: "Lobster", cursive;
  font-size: 1.3em;
  line-height: 0.8em;
}

.side .terminal {
  font-family: "JetBrains Mono", monospace;
  font-size: 1em;
  line-height: 0.8em;
  color: var(--right-color);
}

#left-side {
  background-color: var(--dark);
  width: 60%;
  z-index: 2;
}

#left-side .title {
  color: white;
}

#left-side .fancy {
  color: var(--right-color);
}

#right-side {
  background-color: var(--right-color);
}

#right-side .title {
  color: var(--dark);
}

#right-side .fancy {
  color: white;
}
</style>
