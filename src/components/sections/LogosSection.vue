<template>
  <section class="logos section">
    <div class="logos__container container grid">
      <div v-for="logo in logos" :key="logo.src" class="logos__content">
        <img :src="logo.src" alt="" class="logos__img" />
      </div>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      logos: [
        { src: require("@/assets/img/logo1.png") },
        { src: require("@/assets/img/logo2.png") },
        { src: require("@/assets/img/logo3.png") },
        { src: require("@/assets/img/logo4.png") },
        { src: require("@/assets/img/logo5.png") },
        { src: require("@/assets/img/logo6.png") },
      ],
    };
  },
};
</script>

<style scoped>
.logos__img {
  width: 40px;
  opacity: 0.4;
  transition: 0.3s;
}

.logos__container {
  grid-template-columns: repeat(3, max-content);
  justify-content: center;
  align-items: center;
  gap: 4rem;
  padding-bottom: 2rem;
}

.logos__img:hover {
  opacity: 1;
}

@media screen and (max-width: 320px) {
  .logos__container {
    gap: 2.5rem;
  }
}

@media screen and (min-width: 767px) {
  .logos__container {
    gap: 4rem 8rem;
  }
}

@media screen and (min-width: 1040px) {
  .logos__container {
    grid-template-columns: repeat(6, max-content);
  }

  .logos__img {
    width: 50px;
  }
}
</style>
