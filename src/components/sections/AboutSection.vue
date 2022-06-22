<template>
  <section class="about section" id="about">
    <div class="about__container container grid">
      <div class="about__group">
        <img src="@/assets/img/about.png" alt="" class="about__img" />

        <div class="about__card">
          <h3 class="about__card-title">2.500+</h3>
          <p class="about__card-description">
            Суперзарядки на популярных маршрутах
          </p>
        </div>
      </div>

      <div class="about__data">
        <h2 class="about__title section__title">
          Машины с
          <br />
          технологией будущего
        </h2>

        <p class="about__description">
          Смотрите в будущее с высокопроизводительными электромобилями
          производства известные бренды. Они имеют футуристические конструкции и
          конструкции с новые и инновационные платформы, которые служат долго.
        </p>

        <a href="#" class="button">Узнать больше</a>
      </div>
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style scoped>
.about__container {
  row-gap: 6rem;
}

.about__group {
  position: relative;
}

.about__img {
  width: 310px;
  border-radius: 0.5rem;
}

.about__card {
  width: 180px;
  position: absolute;
  right: 0;
  bottom: -2.5rem;
  background-color: hsla(0, 0%, 100%, 0.1);
  backdrop-filter: blur(16px);
  padding: 1rem 0.75rem;
  text-align: center;
  border-radius: 1.25rem;
}

.about__card-title {
  font-size: var(--h3-font-size);
  margin-bottom: 0.5rem;
}

.about__card-description {
  font-size: var(--smaller-font-size);
}

.about__title {
  text-align: initial;
  margin-bottom: 2rem;
}

.about__description {
  margin-bottom: 2rem;
}

@media screen and (max-width: 320px) {
  .about__card {
    width: 150px;
  }
}

@media screen and (min-width: 576px) {
  .about__group {
    width: 350px;
    justify-self: center;
  }
}

@media screen and (min-width: 767px) {
  .about__container {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media screen and (min-width: 1040px) {
  .about__container {
    column-gap: 6rem;
    align-items: center;
  }

  .about__group,
  .about__img {
    width: 480px;
  }

  .about__card {
    width: 198px;
    padding: 1rem 1.25rem;
  }

  .about__description {
    padding-right: 4rem;
    margin-bottom: 3rem;
  }
}
</style>
