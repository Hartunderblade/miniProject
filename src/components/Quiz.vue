<template>

    <div class="quiz">
        <h2>{{ currentQuestion.question }}</h2>
  <ul>
    <li v-for="option in currentQuestion.options" :key="option.id">
      <input type="radio" :id="option.id" :value="option" v-model="selectedOption">
      <label :for="option.id">{{ option.text }}</label>
    </li>
  </ul>
  <button @click="beforeAnswer">Назад</button>
  <button @click="doneAnswer">Далее</button>
    </div>

</template>
  
<script>
  
  export default {
    data(){
        return{
            currentQuestionIndex: 0,
    selectedOption: null,
    questions: [
      {
        question: 'Вопрос 1',
        options: [
          { id: 1, text: 'Ответ 1' },
          { id: 2, text: 'Ответ 2' },
          { id: 3, text: 'Ответ 3' }
        ],
        correctOptionId: 2
      },
      {
        question: 'Вопрос 2',
        options: [
          { id: 4, text: 'Ответ 1' },
          { id: 5, text: 'Ответ 2' },
          { id: 6, text: 'Ответ 3' }
        ],
        correctOptionId: 4
      }
    ]

  
        }
    },
    computed:{
        currentQuestion() {
        return this.questions[this.currentQuestionIndex];
    }
    },
        methods: {
            doneAnswer() {
      if (this.selectedOption && this.selectedOption.id === this.currentQuestion.correctOptionId) {
        alert('Правильный ответ');
      } else {
        alert('Неправильный ответ');
      }
      this.selectedOption = null;
      this.currentQuestionIndex++;
    },
    beforeAnswer(){
        this.currentQuestionIndex--;
    }
        },
        components: {

        }
    }
  
  </script>
  
  
  <style scoped>

  </style>
  