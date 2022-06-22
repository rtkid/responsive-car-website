<template>
  <section class="offer section">
    <div class="offer__container container grid">
      <img src="@/assets/img/offer-bg.png" alt="" class="offer__bg" />

      <div class="offer__data">
        <h2 class="section__title offer__title">
          Вы Хотите Получать
          <br />
          Cпециальные Предложения?
        </h2>

        <p class="offer__description">
          Получайте первыми всю информацию о нашем продукте и о новых
          автомобилях по электронной почте, подписавшись на нашу рассылку.
        </p>

        <a href="#" class="button"> Подписаться </a>
      </div>

      <img src="@/assets/img/offer.png" alt="" class="offer__img" />
    </div>
  </section>
</template>

<script>
export default {};
</script>

<style scoped>
.offer {
  position: relative;
}

.offer__container {
  grid-template-rows: max-content 224px;
}

.offer__bg {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: center;
}

.offer__data,
.offer__img {
  position: relative;
}

.offer__data {
  text-align: center;
}

.offer__title {
  margin-bottom: 2rem;
}

.offer__description {
  margin-bottom: 3rem;
}

.offer__img {
  position: absolute;
  max-width: initial;
  width: 400px;
  bottom: 2rem;
  right: -5.5rem;
}

@media screen and (max-width: 320px) {
  .offer__container {
    grid-template-rows: max-content 180px;
  }

  .offer__img {
    width: 340px;
  }
}

@media screen and (min-width: 576px) {
  .offer__container {
    grid-template-rows: initial;
    grid-template-columns: 0.5fr;
    justify-content: center;
  }

  .offer__img {
    position: relative;
    bottom: initial;
    right: initial;
  }

  .offer__data {
    margin-bottom: 4rem;
  }
}

@media screen and (min-width: 1040px) {
  .offer__container {
    grid-template-columns: repeat(2, 1fr);
    column-gap: 5rem;
    align-items: center;
    padding-bottom: 2rem;
  }
  .offer__data,
  .offer__title {
    text-align: initial;
  }

  .offer__data {
    margin-bottom: 0;
  }

  .offer__description {
    padding-right: 6rem;
  }

  .offer__img {
    width: 450px;
  }
}
</style>
