
<template>

    <div class="container">
      <div class="text">
        <h2 class="main-text">Список дел</h2>
      </div>
    <div class="container-input">
      <input type="text" @keypress.enter="addNewNote" v-model="newNote" placeholder="Сделайте заметку">
      <button @click="addNewNote">Добавить</button>
    </div>
    <div class="container-toDo" v-for="(note, index) in notes" :key="index">
        <span class="container-toDo__text" :style="{ textDecoration: isChecked ? 'line-through' : 'none', color: isChecked ? 'grey' : 'black' }">{{note}}</span>
        <input type="checkbox" @click="doneNote(event)" v-model="isChecked">
        <button @click="deleteNote(index)">Удалить</button>
        
        
      <!-- <div>
        <button @click="editNote()">Редактировать</button>
      </div> -->
      
    </div>
    </div>
    


    
  </template>
  
  <script>
  export default {
    data(){
      return{
        newNote:'',
        notes:[],
        isChecked: false,
        // isEdit: false,
        
        
       
      
  
      }
    },
    methods: {
    addNewNote(){
            if(this.newNote !== ''){
              this.notes.push(this.newNote);
              this.newNote = '';
            }
        },
        doneNote(event){
          // this.isChecked.push(index.target.value) = !this.isChecked.push(index.target.value);
          this.isChecked.push(event.target.index)
        },
        deleteNote(index) {
      this.notes.splice(index, 1);
    }
        // editNote(index){
        //   this.newNote = this.notes[index];
        //   this.editedIndex = index;
        // }
        // editNote(){
        //   note.isEdit = true;
        // }
      
    },
  }
  
  </script>
  
  
  <style>
  *{
    padding: 0;
    margin: 0;
  }
  .container{
    margin: 20px 50px;
    width: 1020px;
  }
  .main-text{
    font-family:Arial;
    font-size: 18px;
  }
  .text{
    border-bottom: 2px solid rgb(213, 55, 81);
    width: 120px;

    padding: 0 0 6px 0 ;
  }
  .container-input{
    display: flex;
    gap: 100px;

    border-bottom: 1px solid rgb(213, 55, 81);
    padding: 30px 0 ;
    
  }
  .container-input input{
    outline: none;
    /* border: none; */

    /* padding: 20px 0 10px 10px; */

  }
  .container-input button{
    background-color:rgb(211, 64, 88);
    color: #fff;
    border: none;
    font-weight: bold;
    font-size: 13px;
    padding: 10px 30px;
    border-radius: 5px;
    cursor: pointer;
  }
  .container-toDo{
    width: 300px;
    margin: 30px 0;

    padding: 10px 0;

    border-bottom: 1px solid rgb(198, 198, 198);

    display: flex;
    justify-content: space-between;
  }


  </style>
  