<script setup>
import TheIntro from "../Intro/TheIntro.vue";
import "./General.scss";
import "./Logo.scss";
</script>

<template>
  <main
    @mousemove="startTextAnimation"
    @mouseleave="stopTextAnimation"
    :style="{ '--x': x, '--y': y }"
  >
    <section class="section">
      <div class="container">
        <TheIntro />
      </div>
    </section>
  </main>
</template>

<script>
export default {
  data() {
    return {
      x: 0.5,
      y: 0.5,
    };
  },
  methods: {
    startTextAnimation(e) {
      this.x = (e.clientX / window.innerWidth).toFixed(2);
      this.y = (e.clientY / window.innerWidth).toFixed(2);
    },
    stopTextAnimation() {
      this.x = 0.5;
      this.y = 0.5;
    },
  },
};
</script>
