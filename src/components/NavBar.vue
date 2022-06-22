<template>
  <header class="header" id="header">
    <nav class="nav container">
      <a href="" class="nav__logo">
        <i class="ri-steering-line"></i>
        Электрокар
      </a>

      <div class="nav__menu" :class="{ 'show-menu': isOpen }">
        <ul class="nav__list">
          <li
            @click="isOpen = false"
            v-for="link in links"
            :key="link.title"
            class="nav__item"
          >
            <a :href="'#' + link.id" class="nav__link">{{ link.title }}</a>
          </li>
        </ul>

        <div @click="isOpen = false" class="nav__close">
          <i class="ri-close-line"></i>
        </div>
      </div>

      <div @click="isOpen = true" class="nav__toggle">
        <i class="ri-menu-line"></i>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  mounted() {
    window.addEventListener("scroll", this.scrollHeader);
    window.addEventListener("scroll", this.scrollActive);
  },

  unmounted() {
    window.removeEventListener("scroll", this.scrollHeader);
    window.removeEventListener("scroll", this.scrollActive);
  },

  data() {
    return {
      isOpen: false,
      links: [
        { id: "home", title: "Домой" },
        { id: "about", title: "Обо мне" },
        { id: "popular", title: "Рекомендации" },
        { id: "featured", title: "Возможности" },
      ],
    };
  },

  methods: {
    scrollHeader() {
      const header = document.getElementById("header");

      if (window.scrollY >= 50) header.classList.add("scroll-header");
      else header.classList.remove("scroll-header");
    },

    scrollActive() {
      const scrollY = window.scrollY;

      this.links.forEach((link) => {
        const section = document.getElementById(link.id);
        const sectionHeight = section.offsetHeight;
        const sectionTop = section.offsetTop - 50;

        const htmlLink = document.querySelector(
          ".nav__menu a[href*=" + link.id + "]"
        );

        if (scrollY > sectionTop && scrollY <= sectionTop + sectionHeight) {
          htmlLink.classList.add("active-link");
        } else {
          htmlLink.classList.remove("active-link");
        }
      });
    },
  },
};
</script>

<style scoped>
.header {
  width: 100%;
  background-color: transparent;
  position: fixed;
  top: 0;
  left: 0;
  z-index: var(--z-fixed);
}

.nav {
  height: var(--header-height);
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.nav__logo,
.nav__toggle {
  color: var(--title-color);
  display: inline-flex;
}

.nav__logo {
  align-items: center;
  column-gap: 0.25rem;
  font-weight: var(--font-medium);
  transition: 0.3s;
}

.nav__logo i {
  font-size: 1.25rem;
}

.nav__logo:hover {
  color: var(--first-color);
}

.nav__toggle {
  font-size: 1.25rem;
  cursor: pointer;
}

@media screen and (max-width: 767px) {
  .nav__menu {
    position: fixed;
    background-color: hsla(0, 0%, 100%, 0.1);
    top: 0;
    right: -100%;
    width: 100%;
    height: 100%;
    backdrop-filter: blur(96px);
    transition: 0.3s;
  }
}

.nav__list {
  display: flex;
  flex-direction: column;
  text-align: center;
  row-gap: 3rem;
  padding-top: 9rem;
}

.nav__link {
  text-transform: uppercase;
  color: var(--title-color);
  font-size: var(--h2-font-size);
  font-weight: var(--font-medium);
  transition: 0.3s;
}

.nav__link:hover {
  color: var(--first-color);
}

.nav__close {
  font-size: 2rem;
  color: var(--white-color);
  position: absolute;
  top: 1rem;
  right: 1rem;
  cursor: pointer;
}

.show-menu {
  right: 0;
}

.scroll-header {
  border-radius: 0 0 1rem 1rem;
  background-color: var(--body-color);
  box-shadow: 0 2px 4px hsla(0, 0%, 1%, 1);
}

.active-link {
  color: var(--first-color);
}

@media screen and (min-width: 767px) {
  .nav {
    height: calc(var(--header-height) + 1.5rem);
  }

  .nav__toggle,
  .nav__close {
    display: none;
  }

  .nav__list {
    flex-direction: row;
    column-gap: 3rem;
    padding-top: 0;
  }

  .nav__link {
    font-size: var(--normal-font-size);
    text-transform: initial;
  }
}
</style>
