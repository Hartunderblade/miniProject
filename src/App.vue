
<template>
  <div>
    <!-- <Culc/> -->
  </div>
  <div>
    <ToDoLists/>
  </div>
  <div>
    <Slider/>
  </div>
  <div>
    <Convector/>
  </div>
  <div><Quis/></div>
 

    
  
</template>

<script>
import Culc from './components/Culc.vue'
import Slider from './components/Slider.vue'
import ToDoLists from './components/ToDoLists.vue'
import Convector from './components/Convector.vue'
import Quis from './components/Quiz.vue'


export default {
  props: ['data'],
  data(){
    return{

      

    }
  },
  methods: {
  
  },
  components: {
			Culc,
      ToDoLists,
      Slider,
      Convector,
      Quis
		}
}

</script>


<style scoped>

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
/* header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
} */
</style>
