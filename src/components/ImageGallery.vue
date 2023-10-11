<template>
  <div class="gallery">
    <div v-for="(image, index) in images" :key="index" class="image-container">
      <img
        :src="image.thumbnail"
        :alt="image.description"
        @click="showDetails(image)"
      />
    </div>
  </div>
</template>

<script>
export default {
  name: "ImageGallery",
  data() {
    return {
      images: [
        {
          thumbnail: "image1-thumbnail.jpg",
          fullSize: "image1-full.jpg",
          description: "Image 1",
          details: "Additional details for Image 1",
        },
        // Add more image objects
      ],
    };
  },
  methods: {
    showDetails(image) {
      this.$emit("show-details", image);
    },
  },
};
</script>

<style scoped>
.gallery {
  display: flex;
  flex-wrap: wrap;
}

.image-container {
  width: calc(33.33% - 10px);
  margin: 5px;
  overflow: hidden;
  cursor: pointer;
}

.image-container img {
  width: 100%;
  height: 100%;
  object-fit: cover; /* Crop images to be square */
}
</style>
