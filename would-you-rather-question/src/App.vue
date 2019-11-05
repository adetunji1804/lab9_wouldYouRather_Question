<template>
  <div id="app">
    
    <ComponentQuestion 
    
        v-bind:answer1="answer1"
        v-bind:answer2="answer2"
        v-on:answer-changed="answerChanged">
    </ComponentQuestion>
    <div>
        {{ userSelectionMessage }}
     </div>
  </div>
</template>

<script>
import ComponentQuestion from './components/ComponentQuestion.vue'
export default {
  name: 'app',
  data:function(){
    return{
      answer1: '',
      answer2: '',
      userSelectionMessage: '',
      questions:[

        {
        id:0,
        question: 'live in a triangle shaped house or a circle shaped house',
        answer1: 'Live in a triangle house',
        ansewr2: 'Live in a circle house'
        },
        {
        id:1,
        question: 'be a wizard or a superhero?',
        answer1: 'Be a wizard',
        ansewr2: 'Be a super hero'
        },
        {
        id:2,
        question: 'have an elephant-sized cat or a cat-sized elephant',
        answer1: 'Have an elephant cat-sized',
        ansewr2: 'Have a cat-sized elephant'
        },
      ]
    }
  },
  components: {
    ComponentQuestion,
  },
 
  methods:{
     answerChanged(answer){
        this.userSelectionMessage =`Thanks! You selected ${answer}`
    },
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 30px;
  padding:30px;
}
li{
  
  border:1px thin gray;
  background: #2c3e50;
}
</style>
