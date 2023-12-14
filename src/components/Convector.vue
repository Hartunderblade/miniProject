<template>
   <div>
        <h2>Конвектор валют</h2>
        <table v-for="(moneys, index) in money" :key="index">
            <tr><th>Страна</th><th>Курс</th></tr>
            <tr><td>{{index}}</td><td>{{moneys}}</td></tr>
        </table>
        <div>
            <p>Введите сумму:</p>
            <input type="number" v-model="amount">
        </div>
        <div>
            <h3>Выберите валюту:</h3>
            <select v-model="fromCurrency" id="fromCurrency">
                <option value="Dollar">Доллар США $</option>
                <option value="Evro">Евро €</option>
                <option value="Vona">Вона Корея ₩</option>
                <option value="Uan">Юань Китай ¥</option>
                <option value="Rub">Рубль Россия ₽</option>
                <option value="Iena">Иена Япония ¥</option>
            </select>
        </div>
        <div>
            <h3>
                Конвертировать в:
            </h3>
            <select v-model="toCurrency" id="toCurrency">
                <option value="Dollar">Доллар США $</option>
                <option value="Evro">Евро €</option>
                <option value="Vona">Вона Корея ₩</option>
                <option value="Uan">Юань Китай ¥</option>
                <option value="Rub">Рубль Россия ₽</option>
                <option value="Iena">Иена Япония ¥</option>
            </select>
        </div>
        <div>
            <button @click="convert">Конвертировать</button>
        </div>
        <div v-if="result">
            <p>Результат: {{result.toFixed(3)}}</p>
        </div>

   </div>
  
  </template>
  
  <script>
  export default {

    data(){
      return{
        amount: 0,
        fromCurrency:'USD',
        toCurrency:'USD',
        money:{
            Dollar:1,
            Evro:0.91,
            Vona:1205.95,
            Uan:7.09,
            Rub: 98.56,
            Iena: 108.79
      },
        result: null
  
      }
    },
    methods: {
        convert(){
        //    const calcConvert =  this.mony[this.toCurrency] / this.mony[this.fromCurrency];
        //     this.convertResult = this.mony * calcConvert;

            this.result = this.amount *(this.money[this.toCurrency] / this.money[this.fromCurrency]);
        },
      
    },
    components: {
              
    }
  }
  
  </script>
  
  
  <style scoped>
  
  </style>
  