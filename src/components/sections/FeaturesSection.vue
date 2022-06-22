<template>
  <section class="features section">
    <h2 class="section__title">Больше возможностей</h2>

    <div class="features__container container grid">
      <div class="features__group">
        <img src="@/assets/img/features.png" alt="" class="features__img" />

        <div
          v-for="feature in features"
          :key="feature.title"
          class="features__card"
          :class="feature.styleClass"
        >
          <h3 class="features__card-title">{{ feature.title }}</h3>
          <p class="features__card-description">
            {{ feature.descriptionBegin }}
            <br />
            {{ feature.descriptionEnd }}
          </p>
        </div>
      </div>
    </div>

    <img src="@/assets/img/map.svg" alt="" class="features__map" />
  </section>
</template>

<script>
export default {
  data() {
    return {
      features: [
        {
          title: "800v",
          descriptionBegin: "Турбо",
          descriptionEnd: "Зарядка",
          styleClass: "features__card-1",
        },
        {
          title: "350",
          descriptionBegin: "Киллометров",
          descriptionEnd: "Дистанция",
          styleClass: "features__card-2",
        },
        {
          title: "480",
          descriptionBegin: "Киллометров",
          descriptionEnd: "Путешествия",
          styleClass: "features__card-3",
        },
      ],
    };
  },
};
</script>

<style scoped>
.features {
  overflow: hidden;
  position: relative;
}

.features__container {
  padding-top: 2rem;
  grid-template-columns: 285px;
  justify-content: center;
}

.features__group {
  display: grid;
  position: relative;
  z-index: 10;
}

.features__img {
  width: 150px;
  justify-self: center;
}

.features__card {
  width: 135px;
  background-color: hsla(0, 0%, 100%, 0.1);
  backdrop-filter: blur(16px);
  border-radius: 1.25rem;
  padding: 0.75rem 2rem;
  text-align: center;
  color: var(--title-color);
  position: absolute;
}

.features__card-1 {
  top: 4rem;
}

.features__card-2 {
  top: 9.5em;
  right: -2rem;
}

.features__card-3 {
  bottom: 2rem;
}

.features__card-title {
  font-size: var(--h3-font-size);
  margin-bottom: 0.25rem;
}

.features__card-description {
  font-size: var(--smaller-font-size);
}

.features__map {
  max-width: initial;
  width: 450px;
  position: absolute;
  top: 8rem;
  left: -3rem;
  margin: auto;
  transform: rotate(-22deg);
}

@media screen and (min-width: 576px) {
  .features__map {
    left: 0;
    right: 0;
  }
}

@media screen and (min-width: 1040px) {
  .features__container {
    padding: 2rem 0 3rem;
  }

  .features__img {
    width: 200px;
  }

  .features__card {
    width: 127px;
    padding: 0.75rem 2.5rem;
  }

  .features__card-1 {
    left: -1rem;
  }

  .features__card-2 {
    right: -2.5rem;
  }

  .features__card-3 {
    bottom: 7rem;
    left: -1rem;
  }

  .features__map {
    width: 650px;
    top: 11rem;
  }
}
</style>
