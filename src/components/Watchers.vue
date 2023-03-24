<script setup>
    import {ref, watch} from 'vue'

    const question = ref('')
    const answer = ref('Questions usually contain a question mark. ;-)')


    //Watch works directly on a ref

    watch(question, async(newQuestion, oldQuestion) => {
        if(newQuestion.indexOf('?') > -1){
            answer.value = 'Thinking...'
            try{
                const res = await fetch('https://yesno.wtf/api')
                answer.value = (await res.json()).answer
            } catch (error){
                answer.value = 'Error! Could not reach the API. ' + error
            }
        }
    })
</script>
<template>
    <p>
        Ask a yes/no question:
    </p>
    <input v-model="question">
    <p>{{ answer }}</p>

</template>