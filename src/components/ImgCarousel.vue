<template>
  <section aria-label="Recent illustration">
    <div class="carousel">
      <button class="carousel-button previous" @click="prevSlide">
        &#171;
      </button>
      <button class="carousel-button next" @click="nextSlide">&#187;</button>
      <ul>
        <li
          v-for="(slide, index) in slides"
          :key="index"
          class="slide"
          :class="{ active: currentIndex === index }"
        >
          <img
            :src="require(`@/assets/main_images/${slide.src}`)"
            :alt="slide.alt"
            :style="{
              opacity: currentIndex === index ? 1 : 0,
              transition: 'opacity 0.8s ease',
            }"
          />
        </li>
      </ul>
    </div>
  </section>
</template>

<script>
export default {
  name: "ImgCarousel",
  data() {
    return {
      currentIndex: 0,
      slides: [
        {
          src: "skyrim.jpg",
          alt: "Défense de Glandouiller",
        },
        {
          src: "sassanos.jpg",
          alt: "Gagner la guerre - Sassanos",
        },
        {
          src: "fight.jpg",
          alt: "Soldier's duel",
        },
      ],
    };
  },
  methods: {
    nextSlide() {
      this.currentIndex = (this.currentIndex + 1) % this.slides.length;
    },
    prevSlide() {
      this.currentIndex =
        (this.currentIndex - 1 + this.slides.length) % this.slides.length; //+this.slides.length in case currentindex=0
    },
  },
  mounted() {
    //Automatically goes to the next slide
    setInterval(() => {
      this.nextSlide();
    }, 5 * 1000); //in milliseconds
  },
};
</script>

<style scoped>
*,
*::before,
*::after {
  box-sizing: border-box; /*determines how the size is calculated, includes padding and borders*/
}

body {
  margin: 0;
}

.carousel {
  width: 65vw;
  height: 100vh;
  position: fixed;
  top: 0;
  right: 10%;
}

.carousel > ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

.slide {
  opacity: 0;
}

.slide > img {
  position: fixed;
  text-align: auto;
  width: auto;
  height: auto;
  max-width: 100%;
  max-height: 100%;
  z-index: -1;
}

.slide.active {
  opacity: 1;
}

.carousel-button {
  position: absolute;
  z-index: 2; /*Makes sure it shows up above the images*/
  background: none;
  border: none;
  font-size: 4rem;
  color: rgba(255, 255, 255, 0.6);
  top: 50%;
  transform: translateY(-50%);
  cursor: pointer;
  border-radius: 0.25rem;
  padding: 0 0.5rem;
  text-shadow: 0 4px 4px rgba(0, 0, 0, 0.4);
}

.carousel-button:hover {
  color: white;
  text-shadow: 0 4px 4px rgba(0, 0, 0, 0.8);
}

.carousel-button.prev {
  left: 1rem;
}

.carousel-button.next {
  right: 1rem;
}
</style>
