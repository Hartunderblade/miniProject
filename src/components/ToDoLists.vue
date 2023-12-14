
<template>
  <div>
     <div>
        <h2>Сделайте запись</h2>
        <div>
            <input type="text" v-model="newNote" placeholder="Введите текст"/>
            <button type="submit" @click="addNote">Добавить запись</button>
        </div>
        <ul>
          <li v-for="(note, index) in notes" :key="index">
            <input type="checkbox" v-model="note.completed">
            <p >{{note.name}}</p>
            <button @click="done(index)">Изменить</button>
            <button @click="deleteNote(index)">удалить</button>
          </li>
        </ul>
    </div>
  </div>
   
  </template>
  
  <script>

  
  export default {

    data(){
      return{
        newNote:'',
        notes:[],
      }
    },
    methods: {
    
     addNote(){
      if(this.newNote !== ''){
        this.notes.push({
          name: this.newNote,
          completed: false
        });
        this.newNote = '';
      }
      

     },
     deleteNote(index) {
          this.notes.splice(index, 1);
        },
        done(index){
          this.newNote = this.notes[index].name;
          this.deleteNote(index);
        }
     
      
      
      
    },

  }
  
  </script>
  
  
  <style scoped>

  </style>
  