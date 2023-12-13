
<template>
  <div>
     <div>
        <h2>Сделайте запись</h2>
        <div>
            <textarea type="text" v-model="newNote" placeholder="Введите текст"/>
            <button type="submit" @click="addNote">Добавить запись</button>
            <!-- <span v-if="searchQuery === note" style="background-color: yellow">{{ note }}</span> -->
        </div>
        
        <div>
          <input type="text" v-model="searchQuery" placeholder="Поиск">
          <button @click="search">Найти</button>
        </div>
    </div>
    <div v-for="(note, index) in notes" :key="index">
          <textarea >{{note}}</textarea>
          
          <button @click="deleteNote">Удалить запись</button>
    </div>
  </div>
   
  
      
    
  </template>
  
  <script>

  
  export default {

    data(){
      return{
        newNote:'',
        notes:[],
        searchQuery:'',
        
  
      }
    },
    methods: {
    
     addNote(){
      if(this.newNote !== ''){
        this.notes.push(this.newNote);
        this.newNote = '';
      }
      

     },
     deleteNote(index) {
          this.notes.splice(index, 1);
        },
        search() {
          // Фильтрация записей по поисковому запросу
          this.notes = this.notes.filter(note => {
            return note.content.toLowerCase().includes(this.searchQuery.toLowerCase());
          });
          this.searchQuery = '';
        }
     
      
      
      
    },

  }
  
  </script>
  
  
  <style scoped>

  </style>
  