<template>
  <section class="home section" id="home">
    <div class="shape shape__big"></div>
    <div class="shape shape__small"></div>

    <div class="home__container container grid">
      <div class="home__data">
        <h1 class="home__title">Выбери лучший автомобиль</h1>

        <h2 class="home__subtitle">Porshe Mission E</h2>

        <h3 class="home__elec">
          <i class="ri-flashlight-fill"></i>
          Электромобиль
        </h3>
      </div>

      <img src="@/assets/img/home.png" alt="" class="home__img" />

      <div class="home__car">
        <div v-for="info in carInfos" :key="info.name" class="home__car-data">
          <div class="home__car-icon">
            <i :class="info.iconClass"></i>
          </div>

          <h2 class="home__car-number">{{ info.value }}</h2>

          <h3 class="home__car-name">{{ info.name }}</h3>
        </div>
      </div>

      <a href="#" class="home__button">ПУСК</a>
    </div>
  </section>
</template>

<script>
export default {
  data() {
    return {
      carInfos: [
        { name: "ТЕМПЕРАТУРА", value: "24°", iconClass: "ri-temp-cold-line" },
        {
          name: "КИЛЛОМЕТРОВ",
          value: "1405",
          iconClass: "ri-dashboard-3-line",
        },
        { name: "БАТТАРЕЯ", value: "94%", iconClass: "ri-flashlight-fill" },
      ],
    };
  },
};
</script>

<style scoped>
.home {
  position: relative;
  overflow: hidden;
}

.home__container {
  position: relative;
  padding-top: 4rem;
  row-gap: 3rem;
}

.home__data {
  text-align: center;
}

.home__title {
  font-size: var(--h1-font-size);
  margin-bottom: 1rem;
}

.home__subtitle {
  font-size: var(--h3-font-size);
  margin-bottom: 0.25rem;
}

.home__elec {
  font-size: var(--small-font-size);
  font-weight: 400;
  color: var(--text-color);
  display: inline;
  align-items: center;
  column-gap: 0.25rem;
}

.home__elec i {
  color: var(--first-color);
}

.home__img {
  width: 280px;
  justify-self: center;
}

.home__car {
  display: flex;
  justify-content: center;
  align-items: center;
  column-gap: 4rem;
  margin-bottom: 2rem;
}

.home__car-name {
  font-size: 0.625rem;
  font-weight: 400;
  color: var(--text-color-light);
}

.home__car-data {
  text-align: center;
}

.home__car-number {
  font-size: var(--h2-font-size);
  font-weight: var(--font-medium);
  margin-bottom: 0.25rem;
}

.home__car-icon {
  background-color: var(--container-color);
  border-radius: 50%;
  padding: 0.376rem;
  display: inline-flex;
  justify-content: center;
  align-items: center;
  font-size: 0.875rem;
  margin-bottom: 0.75rem;
}

.home__button {
  position: relative;
  border: 2px solid hsl(158, 89%, 30%);
  width: 70px;
  height: 70px;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  justify-self: center;
  font-size: var(--small-font-size);
  color: var(--white-color);
  font-weight: var(--font-medium);
}

.home__button::before {
  content: "";
  border: 2px solid hsl(158, 89%, 30%);
  width: 90px;
  height: 90px;
  position: absolute;
  border-radius: 50%;
  box-shadow: 0 0 12px hsl(158, 98%, 43%);
  transition: 0.3s;
  animation: button 3s infinite;
}

.home .shape__big,
.home .shape__small {
  position: absolute;
}

.home .shape__big {
  left: -9rem;
  top: -4rem;
}

.home .shape__small {
  right: -10rem;
  bottom: 3rem;
}

@keyframes button {
  0% {
    box-shadow: 0 0 12px hsl(158, 98%, 43%);
  }
  50% {
    box-shadow: 0 0 24px hsl(158, 98%, 43%);
  }
}

@media screen and (max-width: 320px) {
  .home__car {
    column-gap: 2rem;
  }
}

@media screen and (min-width: 1040px) {
  .home__container {
    padding-top: 2rem;
  }

  .home__img {
    width: 380px;
  }

  .home__car {
    column-gap: 7rem;
  }

  .home__car-icon {
    font-size: 1.25rem;
    margin-bottom: 1rem;
  }
}
</style>
