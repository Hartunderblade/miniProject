<template>
<!-- 
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
    </div> -->


    <div>
      <h1>Опросник: да или нет</h1>
      <div v-if="quationIndex < quationsText.length">
        <h2>{{quationsText[quationIndex].text}}</h2>
        <div>
          <button @click="answerQuestion(true)">Да</button>
          <button @click="answerQuestion(false)">Нет</button>
        </div>
      </div>
      <div v-else>
        <h2>Вы прошли опросник</h2>
        <h3>Правильнве ответы: {{numAnswer}}</h3>
      </div>
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
    ],

    quationIndex: 0,
    numAnswer: 0,

    quationsText:[
      {text: 'Вопрос 1: Vue.js - это фреймворк JavaScript?', answer: true},
      {text: 'Вопрос 2: Vue.js может использоваться для создания одностраничных приложений?', answer: true},
      {text: 'Вопрос 3: Vue.js разработан компанией Facebook?', answer: true},
      {text: 'Вопрос 4: Vue.js поддерживает реактивное программирование?', answer: true},
    ]

  
        }
    },
    computed:{
        currentQuestion() {
        return this.questions[this.currentQuestionIndex];
    }
    },
        methods: {
          answerQuestion(answer){
            if(answer === this.quationsText[this.quationIndex].answer){
              this.numAnswer++;
            }
            this.quationIndex++;
          },
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
  