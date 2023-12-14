
<template>
    <div class="slider">
    <button @click="beforeSlide">Назад</button>
    <img :src="slides[numSlide]" alt="Slide">
    <button @click="afterSlide">Вперёд</button>
  </div>

  <!-- <div class="slider">
    <div class="slider-images">
      <img v-for="(image, index) in images" :src="image" :key="index" :class="{ active: index === currentImageIndex }">
    </div>
    <div class="slider-controls">
      <button class="prev-button" @click="prevImage">&lt;</button>
      <span class="current-image">{{ currentImageIndex + 1 }}</span>
      <span>/</span>
      <span>{{ images.length }}</span>
      <button class="next-button" @click="nextImage">&gt;</button>
    </div>
  </div> -->

  <!-- <div class="carousel">
    <div class="carousel-inner" :style="{transform:`translateX(-${currentIndex * 100}%)`}"> -->
<!--      <div v-for="(item,index) in items" :key="index"  class="carousel-item">-->
<!--        {{item.img}}-->
<!--      </div>-->
        <!-- <img v-for="(item, index) in items" :key="index" :src="item.img" alt="Image">
      <div class="carousel-item">

      </div>

    </div>

    <button @click="prev">Prev</button>
    <button @click="next">Next</button>
  </div> -->
</template>
  
  <script>
  export default {
    data(){
      return{
        slides: [
        "../assets/images/img1.jpg",
        "../assets/images/img2.jpg",
        "../assets/images/img3.jpg"
      ],
      numSlide: 0,





      currentImageIndex: 0,

      image:[
        {
          img:'./assets/images/img1.jpg'
        },
        {
          img:'./assets/images/img2.jpg'
        },
        {
          img:'./assets/images/img3.jpg'
        },
      ]

      };
    },
    methods: {
      next(){
      this.currentIndex = (this.currentIndex + 1) % this.items.length;
    },
    prev(){
      this.currentIndex = (this.currentIndex - 1 + this.items.length) % this.items.length;
    },


    
      beforeSlide(){
        this.numSlide = (this.numSlide - 1 + this.slides.length) % this.slides.length;
      },
      afterSlide(){
        this.numSlide =  (this.numSlide +1) % this.slides.length;
        console.log(this.numSlide);
      }
    },
    components: {
    }
  }
  
  </script>
  
  
  <style >
.slider {
  display: flex;
  align-items: center;
}

button {
  padding: 8px 12px;
  background-color: #ccc;
  border: none;
  cursor: pointer;
}

img {
  max-width: 100%;
  height: auto;
  margin: 0 12px;
}
  </style>


<template>
  <div class="slider">
    <div class="slider-images">
      <img v-for="(image, index) in images" :src="image" :key="index" :class="{ active: index === currentImageIndex }">
    </div>
    <div class="slider-controls">
      <button class="prev-button" @click="prevImage">&lt;</button>
      <span class="current-image">{{ currentImageIndex + 1 }}</span>
      <span>/</span>
      <span>{{ images.length }}</span>
      <button class="next-button" @click="nextImage">&gt;</button>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      currentImageIndex: 0,
      images: [
        'path/to/image1.jpg',
        'path/to/image2.jpg',
        'path/to/image3.jpg',
        'path/to/image4.jpg',
      ],
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
};
</script>

<style>
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
  
