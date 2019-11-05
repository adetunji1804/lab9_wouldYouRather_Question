<template>
    <div>
        <h2>Would You Rather Questions</h2>
        <div>
            <ul> 
                <li v-for="quest in questions" :key="quest.question">{{ quest.question }} </li>
            </ul>

            <input type="radio" v-model="choice" v-bind:value="answer1" v-on:change="$emit('answer-changed', choice)">
            <label>{{ answer1 }}</label>

            <input  type="radio" v-model="choice" v-bind:value="answer2" v-on:change="$emit('answer-changed', choice)">
            <label>{{ answer2 }}</label>

            </div>

    </div>
</template>

<script>
export default {
    name:'ComponentQuestion',
    data:function(){
        return{
            choice:'',
            answer1:'',
            answer2:''
        }
    },
    props:{
        questions: Array,
    },
    methods: {
        
       }
    
}
</script>

<style>

</style>