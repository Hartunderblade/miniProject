<script>
export default {
  data(){
    return{
      currentIndex:0,
      items:[
        {
          img:'../assets/images/img1.jpg'
        },
        {
          img:'../assets/images/img1.jpg'
        },
        {
          img:'../assets/images/img1.jpg'
        },
        {
          img:'../assets/images/img1.jpg'
        },
        {
          img:'../assets/images/img1.jpg'
        },
        {
          img:'../assets/images/img1.jpg'
        }
      ]
    }
  },
  methods:{
    next(){
      this.currentIndex = (this.currentIndex + 1) % this.items.length;
    },
    prev(){
      this.currentIndex = (this.currentIndex - 1 + this.items.length) % this.items.length;
    }
  }
}
</script>

<template>
    <img src="../assets/images/img1.jpg" alt="">
  <div class="carousel">
    <div class="carousel-inner" :style="{transform:`translateX(-${currentIndex * 100}%)`}">
      <div v-for="(item,index) in items" :key="index"  class="carousel-item">
        <img :src="item.img">
      </div>
    </div>
    <button @click="prev">Prev</button>
    <button @click="next">Next</button>
  </div>
</template>

<style scoped>
.carousel {
  position: relative;
  width:800px;
  overflow: hidden;
}

.carousel-inner {

  display: flex;
  justify-content: space-between;
  transition: transform 0.5s ease;

}

.carousel-item {
  flex: 0 0 100%;
  padding: 1rem;
  box-sizing: border-box;
  object-fit: contain;
  width: 100%;
  height: 100%;

}
</style>
