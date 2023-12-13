
<template>
  <!-- <div id="app">
    <div class="stats">
      <h3 class="stats__title">{{"Текущих задач: "+ tasks.length}}</h3>
    </div>
    <task @task_done="delete_task(index)" :key="index" v-for="(data,index) in tasks" :data="data" ></task>
    <div class="add_task">
      <div class="add_task__input ">
          <input placeholder="Новая задача..." type="text" v-model="new_task.title">
          <textarea placeholder="Описание" type="text" v-model="new_task.desc"></textarea>
      </div>
      <button class="add_task__btn" @click="add_task">➕</button>
    </div>
    
  </div> -->
  <!-- <div class="task">
    <div>
      <h3 class="task__title">{{data.title}}</h3>
      <p v-if="data.desc!=''" class="task__desc">{{data.desc}}</p>
    </div>
    <button class="task__done" @click="task_done()">✔️</button>
  </div> --> 
  <div>
    <!-- <CheckList/> -->
  </div>
  <div>
    <!-- <Culc/> -->
  </div>
  <div>
    <!-- <ToDoLists/> -->
  </div>
  <div>
    <Slider/>
  </div>
  <div>
    <!-- <Convector/> -->
  </div>
  <!-- <div><Quis/></div> -->
 

    
  
</template>

<script>
import CheckList from './components/CheckList.vue'
import Culc from './components/Culc.vue'
import Slider from './components/Slider.vue'
import ToDoLists from './components/ToDoLists.vue'
import Convector from './components/Convector.vue'
import Quis from './components/Quiz.vue'


export default {
  props: ['data'],
  data(){
    return{

      sliderItems:[
        {id:1, name:'img1', img:'1.jpg'},
        {id:2, name:'img2', img:'2.jpg'},
        {id:3, name:'img3', img:'3.jpg'},
        {id:4, name:'img4', img:'4.jpg'},
        {id:5, name:'img5', img:'5.jpg'},
    ],
      
      clue: 'Введите текст',
        inputValue:'',
        notes:['test'],
        isEdit: false,
    //   string: 'asdasda',
    // new_task: {
    //   title: '',
    //   desc: ''
    // },
    // tasks : [
    //   {
    //     title: 'Изучить основы vue.js',
    //     desc: 'Попробовать написать калькулятор',
    //   },
    //   {
    //     title: 'Прочитать книгу "Vue.js в действии"',
    //     desc: '',
    //   }
    // ]

    }
  },
  methods: {
  
    edit1(oneNote) {
      oneNote.isEdit = true;
	},
	save2(oneNote) {
		oneNote.isEdit = false;
	},
    addNewNote(event){
            this.notes.push(event.target.value);
            this.inputValue = '';
        },
    task_done(){
      this.$emit('task_done')
    },
    add_task(){
      if(this.new_task.title != ''){
        this.tasks.push({
          title: this.new_task.title,
          desc: this.new_task.desc
        });
        this.new_task.title='';
        this.new_task.desc='';
      }
    },
    delete_task(id){
      this.tasks.splice(id,1);
    }
  },
  components: {
			Culc,
      CheckList,
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
