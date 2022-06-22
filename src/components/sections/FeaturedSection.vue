<template>
  <section class="featured section" id="featured">
    <h2 class="section__title">Премиальные Автомобили</h2>

    <div class="featured__container container">
      <ul class="featured__filters">
        <li v-for="brand in brands" :key="brand.src">
          <button
            @click="activateFeatured(brand)"
            class="featured__item"
            :data-filter="brand.filterClass"
            :class="{ 'active-featured': brand.isSelected }"
          >
            <img v-if="brand.haveImg" :src="brand.src" alt="" />

            <span v-if="brand.haveText">{{ brand.text }}</span>
          </button>
        </li>
      </ul>

      <div class="featured__content grid">
        <article
          v-for="car in cars"
          :key="car.name"
          class="featured__card mix"
          :class="car.filterClass"
        >
          <div class="shape shape__smaller"></div>

          <h1 class="featured__title">{{ car.brand }}</h1>

          <h3 class="featured__subtitle">{{ car.name }}</h3>

          <img :src="car.imgSrc" alt="" class="featured__img" />

          <h3 class="featured__price">{{ car.price }}</h3>

          <button class="button featured__button">
            <i class="ri-shopping-bag-2-line"></i>
          </button>
        </article>
      </div>
    </div>
  </section>
</template>

<script>
import mixitup from "mixitup";

export default {
  mounted() {
    const containerEl = document.querySelector(".featured__content");
    mixitup(containerEl);
  },

  data() {
    return {
      brands: [
        {
          isSelected: true,
          haveImg: false,
          haveText: true,
          text: "Все",
          filterClass: "all",
        },
        {
          isSelected: false,
          haveImg: true,
          haveText: false,
          src: require("@/assets/img/logo3.png"),
          filterClass: ".tesla",
        },
        {
          isSelected: false,
          haveImg: true,
          haveText: false,
          src: require("@/assets/img/logo2.png"),
          filterClass: ".audi",
        },
        {
          isSelected: false,
          haveImg: true,
          haveText: false,
          src: require("@/assets/img/logo1.png"),
          filterClass: ".porsche",
        },
      ],
      cars: [
        {
          brand: "Tesla",
          name: "Model X",
          price: "$98,900",
          imgSrc: require("@/assets/img/featured1.png"),
          filterClass: "tesla",
        },
        {
          brand: "Tesla",
          name: "Model 3",
          price: "$45,900",
          imgSrc: require("@/assets/img/featured2.png"),
          filterClass: "tesla",
        },
        {
          brand: "Audi",
          name: "E-tron",
          price: "$175,900",
          imgSrc: require("@/assets/img/featured3.png"),
          filterClass: "audi",
        },
        {
          brand: "Porsche",
          name: "Boxster 987",
          price: "$126,900",
          imgSrc: require("@/assets/img/featured4.png"),
          filterClass: "porsche",
        },
        {
          brand: "Porsche",
          name: "Panamera",
          price: "$126,900",
          imgSrc: require("@/assets/img/featured5.png"),
          filterClass: "porsche",
        },
      ],
    };
  },

  methods: {
    activateFeatured(brand) {
      brand.isSelected = true;

      this.brands.forEach((b) => {
        if (brand.filterClass != b.filterClass) {
          b.isSelected = false;
        }
      });
    },
  },
};
</script>

<style scoped>
.featured__container {
  padding-top: 1rem;
}

.featured__filters {
  display: flex;
  align-items: center;
  justify-content: center;
  column-gap: 1rem;
  margin-bottom: 3.5rem;
}

.featured__item {
  width: 48px;
  height: 48px;
  border: none;
  outline: none;
  padding: 0.75rem;
  border-radius: 0.75rem;
  background-color: var(--container-color);
  color: var(--white-color);
  font-size: var(--normal-font-size);
  cursor: pointer;
  transition: 0.3s;
}

.featured_item img {
  width: 1.5rem;
}

.featured__item span,
.featured__item img {
  opacity: 0.3;
  transition: 0.3s;
}

.featured__item:hover {
  background-color: var(--first-color);
}

.featured__item:hover span,
.featured__item:hover img {
  opacity: 1;
}

.featured__content {
  grid-template-columns: 228px;
  row-gap: 2.5rem;
  justify-content: center;
}

.featured__card {
  position: relative;
  background-color: var(--container-color);
  padding: 2rem 1.5rem 1.5rem;
  border-radius: 1rem;
}

.featured__card .shape__smaller {
  position: absolute;
  inset: 0;
  margin: auto;
}

.featured__title,
.featured__subtitle,
.featured__img {
  position: relative;
}

.featured__title {
  font-size: var(--h2-font-size);
  margin-bottom: 0.25rem;
}

.featured__subtitle {
  font-size: var(--normal-font-size);
  color: var(--text-color);
  font-weight: 400;
}

.featured__img {
  width: 180px;
  margin: 1.5rem 0;
  transition: 0.3s;
}

.featured__price {
  font-size: var(--h3-font-size);
}

.featured__button {
  border: none;
  outline: none;
  padding: 0.75rem 1rem;
  position: absolute;
  right: 0;
  bottom: 0;
  border-radius: 1rem 0 1rem 0;
  cursor: pointer;
}

.featured__button i {
  font-size: 1.25rem;
}

.featured__card:hover .featured__img {
  transform: translateX(-0.25rem);
}

.active-featured {
  background-color: var(--first-color);
}

.active-featured span,
.active-featured img {
  opacity: 1;
}

@media screen and (min-width: 576px) {
  .featured__content {
    grid-template-columns: repeat(2, 228px);
  }
}

@media screen and (min-width: 1040px) {
  .featured__container {
    padding-bottom: 2.5rem;
  }

  .featured__filters {
    column-gap: 2rem;
    margin-bottom: 4.5rem;
  }

  .featured__item {
    width: 52px;
    height: 52px;
  }

  .featured__item img {
    width: 2rem;
  }

  .featured__content {
    grid-template-columns: repeat(3, 248px);
    gap: 4rem;
  }
}
</style>
