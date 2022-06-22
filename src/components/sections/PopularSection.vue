<template>
  <section class="popular section" id="popular">
    <h2 class="section__title">
      Выберите свой электромобиль
      <br />
      марки Porsche
    </h2>

    <swiper
      loop
      grabCursor
      :modules="modules"
      :slidesPerView="3"
      :spaceBetween="24"
      class="popular__container container"
      :pagination="{
        el: '.swiper-pagination',
        clickable: true,
        dynamicBullets: true,
      }"
      :breakpoints="{
        '100': {
          slidesPerView: 1,
        },
        '1024': {
          spaceBetween: 48,
        },
      }"
    >
      <swiper-slide v-for="car in cars" :key="car.price" class="popular__card">
        <div class="shape shape__smaller"></div>

        <h1 class="popular__title">{{ car.brand }}</h1>
        <h3 class="popular__subtitle">{{ car.name }}</h3>

        <img :src="car.img" alt="" class="popular__img" />

        <div class="popular__data">
          <div
            v-for="record in car.records"
            :key="record.name"
            class="popular__data-group"
          >
            <i :class="record.iconClass"></i>{{ record.name }}
          </div>
        </div>

        <h3 class="popular__price">{{ car.price }}</h3>

        <button class="button popular__button">
          <i class="ri-shopping-bag-2-line"></i>
        </button>
      </swiper-slide>

      <div class="swiper-pagination"></div>
    </swiper>
  </section>
</template>

<script>
import { Swiper, SwiperSlide } from "swiper/vue";
import { Pagination } from "swiper";

import "swiper/css";
import "swiper/css/pagination";

export default {
  components: {
    Swiper,
    SwiperSlide,
  },

  setup() {
    return {
      modules: [Pagination],
    };
  },

  data() {
    return {
      cars: [
        {
          price: "$175,900",
          brand: "Porshe",
          name: "Turbo S",
          img: require("@/assets/img/popular1.png"),
          records: [
            { name: "3.7 Секунд", iconClass: "ri-dashboard-3-line" },
            { name: "356 Км/ч", iconClass: "ri-funds-box-line" },
            { name: "Электромобиль", iconClass: "ri-charging-pile-2-line" },
          ],
        },
        {
          price: "$114,900",
          brand: "Porshe",
          name: "Taycan",
          img: require("@/assets/img/popular2.png"),
          records: [
            { name: "3.7 Секунд", iconClass: "ri-dashboard-3-line" },
            { name: "356 Км/ч", iconClass: "ri-funds-box-line" },
            { name: "Электромобиль", iconClass: "ri-charging-pile-2-line" },
          ],
        },
        {
          price: "$150,900",
          brand: "Porshe",
          name: "Turbo S Cross",
          img: require("@/assets/img/popular3.png"),
          records: [
            { name: "3.7 Секунд", iconClass: "ri-dashboard-3-line" },
            { name: "356 Км/ч", iconClass: "ri-funds-box-line" },
            { name: "Электромобиль", iconClass: "ri-charging-pile-2-line" },
          ],
        },
        {
          price: "$125,900",
          brand: "Porshe",
          name: "Boxster 718",
          img: require("@/assets/img/popular4.png"),
          records: [
            { name: "3.7 Секунд", iconClass: "ri-dashboard-3-line" },
            { name: "356 Км/ч", iconClass: "ri-funds-box-line" },
            { name: "Электромобиль", iconClass: "ri-charging-pile-2-line" },
          ],
        },
        {
          price: "$128,900",
          brand: "Porshe",
          name: "Cayman",
          img: require("@/assets/img/popular5.png"),
          records: [
            { name: "3.7 Секунд", iconClass: "ri-dashboard-3-line" },
            { name: "356 Км/ч", iconClass: "ri-funds-box-line" },
            { name: "Электромобиль", iconClass: "ri-charging-pile-2-line" },
          ],
        },
      ],
    };
  },
};
</script>

<style>
.popular__container {
  padding-top: 1rem;
}

.popular__card {
  position: relative;
  width: 238px;
  background-color: var(--container-color);
  padding: 2rem 1.5rem 1.5rem;
  border-radius: 1rem;
  margin-bottom: 3.5rem;
  overflow: hidden;
}

.popular__card .shape__smaller {
  position: absolute;
  top: -2.5rem;
  left: -2.5rem;
}

.popular__title,
.popular__subtitle,
.popular__img {
  position: relative;
}

.popular__title {
  font-size: var(--h2-font-size);
  margin-bottom: 0.25rem;
}

.popular__subtitle {
  font-size: var(--normal-font-size);
  color: var(--text-color);
  font-weight: 400;
}

.popular__img {
  width: 160px;
  margin: 0.75rem 0 1.25rem 1.5rem;
  transition: 0.3s;
}

.popular__data {
  display: grid;
  grid-template-columns: repeat(2, max-content);
  gap: 0.5rem 1.25rem;
  margin-bottom: 2rem;
}

.popular__data-group {
  display: inline-flex;
  align-items: center;
  column-gap: 0.5rem;
  font-size: var(--smaller-font-size);
  color: var(--white-color);
}

.popular__data i {
  font-size: 1rem;
}

.popular__price {
  font-size: var(--h3-font-size);
}

.popular__button {
  border: none;
  outline: none;
  padding: 0.75rem 1rem;
  position: absolute;
  right: 0;
  bottom: 0;
  border-radius: 1rem 0 1rem 0;
  cursor: pointer;
}

.popular__button i {
  font-size: 1.25rem;
}

.popular__card:hover .popular__img {
  transform: translateY(-0.25rem);
}

.swiper-pagination-bullet {
  background: var(--text-color);
}

.swiper-pagination-bullet-active {
  background-color: var(--first-color);
}

@media screen and (min-width: 1040px) {
  .popular__container {
    width: 875px;
    padding-top: 3rem;
  }

  .popular__cart {
    width: 258px;
    border-radius: 1.25rem;
    margin-bottom: 5rem;
  }

  .popular__img {
    width: 180px;
    margin: 0.75rem 0 1.25rem 2rem;
  }
}
</style>
