<template>
  <footer class="footer section">
    <div class="shape shape__big"></div>
    <div class="shape shape__small"></div>

    <div class="footer__container container grid">
      <div class="footer__content">
        <a href="#" class="footer__logo">
          <i class="ri-steering-line"></i> Электромобиль
        </a>

        <p class="footer__description">
          Предлагаем лучшие электромобили <br />
          самые узнаваемые бренды <br />
          В мире.
        </p>
      </div>

      <div v-for="info in infos" :key="info.name" class="footer__content">
        <h3 class="footer__title">{{ info.name }}</h3>

        <ul class="footer__links">
          <li v-for="link in info.links" :key="link.name">
            <a href="#" class="footer__link">{{ link.name }}</a>
          </li>
        </ul>
      </div>

      <div class="footer__content">
        <h3 class="footer__title">Подписывайтесь на нас</h3>

        <ul class="footer__social">
          <a
            v-for="social in socials"
            :key="social.iconClass"
            :href="social.href"
            target="_blank"
            class="footer__social-link"
          >
            <i :class="social.iconClass"></i>
          </a>
        </ul>
      </div>
    </div>

    <span class="footer__copy"> &#169; Никита. Все права защищены </span>
  </footer>
</template>

<script>
export default {
  data() {
    return {
      infos: [
        {
          name: "Компания",
          links: [
            { name: "Обо мне" },
            { name: "Машины" },
            { name: "История" },
            { name: "Магазин" },
          ],
        },
        {
          name: "Информация",
          links: [
            { name: "Сделать запрос" },
            { name: "Найти дилера" },
            { name: "Свяжитесь с нами" },
            { name: "Услуги" },
          ],
        },
      ],

      socials: [
        { href: "https://www.facebook.com/", iconClass: "ri-facebook-fill" },
        { href: "https://www.instagram.com/", iconClass: "ri-instagram-line" },
        { href: "https://twitter.com/", iconClass: "ri-twitter-line" },
      ],
    };
  },
};
</script>

<style scoped>
.footer {
  position: relative;
  overflow: hidden;
}

.footer .shape__big,
.footer .shape__small {
  position: absolute;
}

.footer .shape__big {
  width: 300px;
  height: 300px;
  left: -12rem;
  top: 6rem;
}

.footer .shape__small {
  right: -13rem;
  bottom: -6rem;
}

.footer__container {
  row-gap: 2.5rem;
  position: relative;
}

.footer__logo {
  display: inline-flex;
  align-items: center;
  column-gap: 0.25rem;
  color: var(--title-color);
  font-size: var(--h2-font-size);
  font-weight: var(--font-semi-bold);
  margin-bottom: 1.25rem;
  transition: 0.3s;
}

.footer__logo i {
  font-size: 1.5rem;
  font-weight: 500;
}

.footer__logo:hover {
  color: var(--first-color);
}

.footer__title {
  font-size: var(--h3-font-size);
  margin-bottom: 1.25rem;
}

.footer__links {
  display: flex;
  flex-direction: column;
  row-gap: 0.5rem;
}

.footer__link,
.footer__social-link {
  color: var(--text-color);
  transition: 0.3s;
}

.footer__link:hover,
.footer__social-link:hover {
  color: var(--title-color);
}

.footer__social {
  display: flex;
  column-gap: 1.5rem;
}

.footer__social-link {
  font-size: 1.25rem;
}

.footer__copy {
  display: block;
  margin-top: 4.5rem;
  text-align: center;
  font-size: var(--smaller-font-size);
  color: var(--text-color-ligth);
}

@media screen and (min-width: 767px) {
  .footer__container {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media screen and (min-width: 1040px) {
  .footer__container {
    grid-template-columns: repeat(4, max-content);
    justify-content: space-between;
  }

  .footer__logo {
    column-gap: 0.5rem;
  }

  .footer__logo i {
    font-size: 2rem;
  }

  .footer__title {
    margin-bottom: 1.5rem;
  }

  .footer__links {
    row-gap: 0.75rem;
  }

  .footer__social-link {
    font-size: 1.5rem;
  }

  .footer__copy {
    margin-top: 8rem;
    padding-bottom: 1rem;
  }
}
</style>
