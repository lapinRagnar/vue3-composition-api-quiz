<template>

  <div class="question-container">
    <h1 class="question">  {{ question.text }} </h1>
  </div>
  <div class="options-container">
    <div class="option" v-for="(option, index) in question.options" :key="index" @click="emitSelectedOption(option.isCorrect)">
      <p class="option-label"> {{ option.label }} </p>
      <div class="option-value">
        <p> {{ option.text }} </p>
      </div>
    </div>
  </div>      

</template>

<script setup>
  import { defineProps, defineEmits } from 'vue'

  const {question} = defineProps(['question'])

  const emit = defineEmits(['selectOption'])
  const emitSelectedOption = (isCorrect) => {
    emit('selectOption', isCorrect)
  }

</script>

<style lang="scss" scoped>


  .question-container{
    margin-top: 20px;

    .question {
      font-size: 40px;
      margin-bottom: 20px;    
    }
  }

  .options-container {
    
    .option {
      display: flex;
      margin-bottom: 20px;
      cursor: pointer;

      .option-label {
        background-color: bisque;
        width: 60px;
        height: 60px;
        font-size: 30px;
        display: flex;
        align-items: center;
        justify-content: center;
        color: brown;

      }

      .option-value {
        background-color: rgb(149, 121, 121);
        width: 100%;
        font-size: 30px;
        padding: 0px 20px;
        color:rgb(52, 58, 46);
      }
    }
  }
</style>