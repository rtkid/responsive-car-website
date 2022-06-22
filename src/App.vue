<template>
  <nav-bar></nav-bar>
  <main class="main">
    <home-section></home-section>
    <about-section></about-section>
    <popular-section></popular-section>
    <features-section></features-section>
    <featured-section></featured-section>
    <offer-section></offer-section>
    <logos-section></logos-section>
  </main>
  <my-footer></my-footer>
  <scroll-up></scroll-up>
</template>

<script>
import NavBar from "@/components/NavBar.vue";
import HomeSection from "@/components/sections/HomeSection.vue";
import AboutSection from "@/components/sections/AboutSection.vue";
import PopularSection from "@/components/sections/PopularSection.vue";
import FeaturesSection from "@/components/sections/FeaturesSection.vue";
import FeaturedSection from "@/components/sections/FeaturedSection.vue";
import OfferSection from "@/components/sections/OfferSection.vue";
import LogosSection from "@/components/sections/LogosSection.vue";
import MyFooter from "@/components/MyFooter.vue";
import ScrollUp from "@/components/ScrollUp.vue";

export default {
  name: "App",
  components: {
    NavBar,
    HomeSection,
    AboutSection,
    PopularSection,
    FeaturesSection,
    FeaturedSection,
    OfferSection,
    LogosSection,
    MyFooter,
    ScrollUp,
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@100;200;300;400;500;600;700;900&display=swap");

#app {
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}

:root {
  --header-height: 3.5rem;

  --hue-color: 219;

  --first-color: hsl(var(--hue-color), 69%, 56%);
  --first-color-alt: hsl(var(--hue-color), 69%, 52%);
  --title-color: hsl(var(--hue-color), 8%, 95%);
  --text-color: hsl(var(--hue-color), 8%, 75%);
  --text-color-ligth: hsl(var(--hue-color), 4%, 55%);
  --white-color: #fff;
  --body-color: hsl(var(--hue-color), 4%, 4%);
  --container-color: hsl(var(--hue-color), 4%, 7%);

  --body-font: "Roboto", sans-serif;

  --h1-font-size: 1.5rem;
  --h2-font-size: 1.25rem;
  --h3-font-size: 1rem;
  --normal-font-size: 0.938rem;
  --small-font-size: 0.813rem;
  --smaller-font-size: 0.75rem;

  --font-medium: 500;
  --font-semi-bold: 600;

  --z-tooltip: 10;
  --z-fixed: 100;
}

@media screen and (min-width: 968px) {
  :root {
    --h1-font-size: 2.25rem;
    --h2-font-size: 1.5rem;
    --h3-font-size: 1.25rem;
    --normal-font-size: 1rem;
    --small-font-size: 0.875rem;
    --smaller-font-size: 0.813rem;
  }
}

* {
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}

html {
  scroll-behavior: smooth;
}

body {
  line-height: 1.5;
  font-family: var(--body-font);
  font-size: var(--normal-font-size);
  background-color: var(--body-color);
  color: var(--text-color);
}

h1,
h2,
h3,
h4 {
  color: var(--title-color);
  font-weight: var(--font-semi-bold);
}

ul {
  list-style: none;
}

a {
  text-decoration: none;
}

img {
  max-width: 100%;
  height: auto;
}

.container {
  max-width: 1024px;
  margin-right: 1.5rem;
  margin-left: 1.5rem;
}

.grid {
  display: grid;
  gap: 1.5rem;
}

.section {
  padding: 4.5rem 0 2rem;
}

.section__title {
  font-size: var(--h2-font-size);
  text-align: center;
  margin-bottom: 2.5rem;
}

.main {
  overflow: hidden;
}

.shape {
  background-color: hsla(var(--hue-color), 33%, 32%, 0.5);
  filter: blur(112px);
  border-radius: 50%;
}

.shape__big {
  width: 400px;
  height: 400px;
}

.shape__small {
  width: 300px;
  height: 300px;
}

.shape__smaller {
  width: 180px;
  height: 180px;
  filter: blur(64px);
}

.button {
  display: inline-block;
  background-color: var(--first-color);
  color: var(--white-color);
  padding: 1rem 2rem;
  border-radius: 0.25rem;
  font-size: var(--normal-font-size);
  transition: 0.3s;
}

.button:hover {
  background-color: var(--first-color-alt);
}

::-webkit-scrollbar {
  width: 0.6rem;
  background-color: hsl(var(--hue-color), 4%, 16%);
  border-radius: 1rem;
}

::-webkit-scrollbar-thumb {
  background-color: hsl(var(--hue-color), 4%, 24%);
  border-radius: 1rem;
}

::-webkit-scrollbar-thumb:hover {
  background-color: hsl(var(--hue-color), 4%, 32%);
}

@media screen and (max-width: 320px) {
  .container {
    margin-left: 1rem;
    margin-right: 1rem;
  }
}

@media screen and (min-width: 767px) {
  .section {
    padding: 7rem 0 2rem;
  }
}

@media screen and (min-width: 1040px) {
  .container {
    margin-left: auto;
    margin-right: auto;
  }

  .shape__big {
    width: 500px;
    height: 500px;
  }

  .shape__small {
    width: 400px;
    height: 400px;
  }
}
</style>
