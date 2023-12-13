
<template>
    <!-- <h1>слайдер</h1>
    <div class="slider">
    <div class="slider-images" >
        <img v-for="(image, index) in images" :key="index"  :src="image"  :class="{ active: index === currentImageIndex }">
    </div>
    <div class="slider-controls">
      <button class="prev-button" @click="prevImage">&lt;</button>
      <span class="current-image">{{ currentImageIndex + 1 }}</span>
      <span>/</span>
      <span>{{ images.length }}</span>
      <button class="next-button" @click="nextImage">&gt;</button>
    </div>
  </div> -->

  <!-- <div >
    <img v-for="image in images" :key="image" :src="image" alt="imgG">
  </div> -->
  <div>
    <img src="../assets/images/img1.jpg" alt="">
  </div>
  <div v-for="slide in slides" :key="slide">
    <img :src="slide.image" alt="">
  </div>
</template>
  
  <script>
  export default {
    data(){
      return{
    
      slides: [
        {image: require('@/assets/images/img1.jpg')},
        {image: require('@/assets/images/img2.jpg')},
        {image: require('@/assets/images/img3.jpg')},
        {image: require('@/assets/images/img5.jpg')},
      ],

          // currentImageIndex: 0,
      };
    },
    methods: {
      prevImage() {
      if (this.currentImageIndex > 0) {
        this.currentImageIndex--;
      } else {
        this.currentImageIndex = this.images.length - 1;
      }
    },
    nextImage() {
      if (this.currentImageIndex < this.images.length - 1) {
        this.currentImageIndex++;
      } else {
        this.currentImageIndex = 0;
      }
    },

    },
    components: {
    }
  }
  
  </script>
  
  
  <style >
.slider {
  position: relative;
  width: 100%;
}

.slider-images {
  display: flex;
  overflow: hidden;
}

.slider-images img {
  width: 100%;
  height: auto;
  opacity: 0;
  transition: opacity 0.5s ease;
}

.slider-images img.active {
  opacity: 1;
}

.slider-controls {
  position: absolute;
  bottom: 20px;
  left: 50%;
  transform: translateX(-50%);
  display: flex;
  align-items: center;
}

.slider-controls button {
  border: none;
  background-color: transparent;
  outline: none;
  font-size: 24px;
  cursor: pointer;
}

.slider-controls .current-image {
  margin: 0 10px;
}
  </style>
  