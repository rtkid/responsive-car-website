<template>
  <a href="#" class="scrollup" id="scroll-up">
    <i class="ri-arrow-up-line"></i>
  </a>
</template>

<script>
export default {
  mounted() {
    window.addEventListener("scroll", this.handleScroll);
  },

  unmounted() {
    window.removeEventListener("scroll", this.handleScroll);
  },

  methods: {
    handleScroll() {
      const scrollUp = document.getElementById("scroll-up");
      if (window.scrollY >= 560) scrollUp.classList.add("show-scroll");
      else scrollUp.classList.remove("show-scroll");
    },
  },
};
</script>

<style scoped>
.scrollup {
  position: fixed;
  right: 1rem;
  bottom: -30%;
  background-color: hsla(0, 0%, 100%, 0.1);
  backdrop-filter: blur(15px);
  display: inline-flex;
  padding: 0.45rem;
  border-radius: 0.5rem;
  font-size: 1.15rem;
  color: var(--white-color);
  z-index: var(--z-tooltip);
  transition: 0.4s;
}

.scrollup:hover {
  transform: translateY(-0.25rem);
}
.show-scroll {
  bottom: 3rem;
}

@media screen and (min-width: 1040px) {
  .scrollup {
    right: 3rem;
  }
}
</style>
