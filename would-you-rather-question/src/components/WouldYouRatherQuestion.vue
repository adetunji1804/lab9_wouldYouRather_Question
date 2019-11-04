<template>
    
    <div>
         <h1>Would you rather....</h1>
        <WouldYouRatherQuestion 
        v-bind:question="question"
        v-bind:answer1="answer1"
        v-bind:answer2="answer2"
        v-on:answer-changed="answerChanged">

        </WouldYouRatherQuestion>
    </div>

</template>

<script>

 const wouldYouRatherQuestionComponent ={
            template: `
            <div>

            <input type="radio" v-model="choice" v-bind:value="answer1" v-on:change="$emit('answer-changed', choice)">
            <label>{{ answer1 }}</label>

            <input type="radio" v-model="choice" v-bind:value="answer2" v-on:change="$emit('answer-changed', choice)">
            <label>{{ answer2 }}</label>

            </div>
            `,
            data(){ // data - for internal data that belongs to this component
                return{
                    choice: ''
                }
            },
            props: { //props - for data passed in from parent component
                question: String,
                answer1: String,
                answer2: String
            }
    }

export default {
    name:'WouldYouRatherQuestion',
    data:function(){
        return{
            id: '',
            question: '',
            answer1: '',
            answer2: '',
            userSelectionMessage: ''
        }
    },
    methods: {
                answerChanged(answer){
                   // console.log("Event emitted from child")
                   this.userSelectionMessage =`Thanks! You selected ${answer}`
            }

    },
    
}
</script>

<style>

</style>