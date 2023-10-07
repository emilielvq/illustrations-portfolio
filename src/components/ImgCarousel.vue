<template>
  <section aria-label="Recent illustration">
    <div class="carousel">
      <button class="carousel-button previous">&#171;</button>
      <button class="carousel-button next">&#187;</button>
      <ul>
        <li class="slide" :class="{ active: currentIndex === 0 }">
          <img src="../assets/skyrim.jpg" alt="Défense de Glandouiller" />
        </li>
        <li class="slide" :class="{ active: currentIndex === 1 }">
          <img src="../assets/sassanos.jpg" alt="Gagner la guerre - Sassanos" />
        </li>
        <li class="slide" :class="{ active: currentIndex === 2 }">
          <img src="../assets/fight.jpg" alt="Soldier's duel" />
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
      currentIndex: 0, // Initialize the active slide index
    };
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
  width: 50vw;
  height: 100vh;
  position: relative;
}

.carousel > ul {
  margin: 0;
  padding: 0;
  list-style: none;
}

.slide {
  position: absolute;
  inset: 0;
  opacity: 0;
}

.slide > img {
  position: fixed;
  right: 0;
  top: 0;
  width: auto;
  height: auto;
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
