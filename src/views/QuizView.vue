<template>  
  <div>

    <QuizHeader
      :questionStatus="questionStatus"
      :barPercentage="barPercentage"
    />

    <div>
      <Question
        v-if="!showResults"
        :question="quiz.questions[currentQuestionIndex]" 
        @selectOption="onOptionSelected"
      />

      <Result
        v-else
        :quizQuestionLength="quiz.questions.length"
        :numberOfCorrectAnswers="numberOfCorrectAnswers"
      />
    </div>

  </div>
</template>

<script setup>
  import Question from '@/components/Question.vue';
  import QuizHeader from '@/components/QuizHeader.vue'
  import Result from '@/components/Result.vue'

  import { computed, ref, watch } from 'vue';
  import { useRoute } from 'vue-router'
  import quizes from '@/data/quize.json'

  const route = useRoute()
  const quizId = parseInt(route.params.id)
  const quiz = quizes.find(q => q.id === quizId)
  const currentQuestionIndex = ref(0)
  const numberOfCorrectAnswers = ref(0)
  const showResults = ref(false)

  const questionStatus = computed(() => {
    return `${currentQuestionIndex.value}/${quiz.questions.length}`
  })

  const barPercentage = computed(() => {
    return `${currentQuestionIndex.value/quiz.questions.length * 100}%`
  })

  const onOptionSelected = (isCorrect) => {
    console.log('la valeur recue', isCorrect)
    if (isCorrect) {
      numberOfCorrectAnswers.value++
    }
    if (quiz.questions.length -1 === currentQuestionIndex.value) {
      showResults.value = true
    }
    currentQuestionIndex.value++
  }

</script>

// est l'equivalent de computed()
// const questionStatus = ref(`${currentQuestionIndex.value}/${quiz.questions.length}`)
  
// watch(() => currentQuestionIndex.value, () => {
//   questionStatus.value = ref(`${currentQuestionIndex.value}/${quiz.questions.length}`)
// })

