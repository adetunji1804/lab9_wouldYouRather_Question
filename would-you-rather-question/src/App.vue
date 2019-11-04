<template>
  <div id="app">
    <ul>
      <li v-for="question in questions" v-bind:key="question.question">{{ question }}</li>
    </ul>
    <WouldYouRatherQuestion></WouldYouRatherQuestion>
  </div>
</template>

<script>
import WouldYouRatherQuestion from './components/WouldYouRatherQuestion.vue'

export default {
  name: 'app',
  data:function(){
    return{
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
        }
      ]
    }
  },
  components: {
    WouldYouRatherQuestion
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
  margin-top: 60px;
}
</style>
