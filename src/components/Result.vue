<script setup>
  import { defineProps} from 'vue'

  const { quizQuestionLength, numberOfCorrectAnswers } = defineProps(['quizQuestionLength', 'numberOfCorrectAnswers'])

</script>

<template>
  <div class="results">
    <p>Your results..</p>
    <h1> {{ numberOfCorrectAnswers }}/{{ quizQuestionLength }} </h1>
    
    <RouterLink to="/"> Retour </RouterLink>
  </div>
</template>

<style scoped lang="scss">
  .results {
    text-align: center;
    padding: 100px 0px;

    p {
      font-size: 25px;
    }

    h1 {
      font-size: 80px;
    }
  }
</style>