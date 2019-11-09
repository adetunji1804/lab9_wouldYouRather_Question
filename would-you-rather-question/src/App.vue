<template>
  <div id="app">
    <ComponentQuestion v-for="q in questions" v-bind:key="q.id"
      v-bind:question="q.question"
      
      v-bind:answer2="q.answer2"
      v-bind:answer1="q.answer1"
      v:bind:id="q.id"
      v-bind:id="q.id"
      v-bind:selection-changed="selectionChanged"
      >   
      </ComponentQuestion>
       <h4>You would rather...</h4>
       
  <ol>
    <li v-for="choice in choices" :key="choice">{{ choice }} </li>

  </ol>
  </div>
</template>

<script>
import ComponentQuestion from './components/ComponentQuestion.vue'
export default {
  name: 'app',
  data:function(){
    return{
      questions:[

        {
        id:0,
        question: 'live in a triangle shaped house or a circle shaped house',
        answer1: 'Live in a triangle house',
        answer2: 'Live in a circle house'
        },
        {
        id:1,
        question: 'be a wizard or a superhero?',
        answer1: 'Be a wizard',
        answer2: 'Be a super hero'
        },
        {
        id:2,
        question: 'have an elephant-sized cat or a cat-sized elephant',
        answer1: 'Have an elephant cat-sized',
        answer2: 'Have a cat-sized elephant'
        }
      ],
      
      choices: []
  
  }
  },
    components: {
     ComponentQuestion 
  } ,
  methods:{
    selectionChanged(choice, id)
    {
        this.choices.push(choice, id)
    }
  }
}

</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: left;
  color: #2c3e50;
  margin-top: 30px;
  padding:30px;
}

</style>
