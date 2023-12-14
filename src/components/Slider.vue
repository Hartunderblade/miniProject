
<template>
    <div class="slider">
    <button @click="beforeSlide">Назад</button>
    <img :src="slides[numSlide]" alt="Slide">
    <button @click="afterSlide">Вперёд</button>
  </div>
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
      numSlide: 0

      };
    },
    methods: {
      beforeSlide(){
        this.numSlide = (this.numSlide - 1 + this.slides.length) % this.slides.length;
      },
      afterSlide(){
        this.numSlide =  (this.numSlide +1) % this.slides.length;
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
  