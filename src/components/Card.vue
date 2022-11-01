<template>

  <div class="card">
    <img :src="quiz.img" alt="">
    <div class="card-text">
      <h2>{{ quiz.name  }}</h2>
      <p> {{ quiz.questions.length }} questions</p>
    </div>
  </div>

</template>

<script setup>
  import { defineProps } from 'vue'

  const { quiz } = defineProps(['quiz'])

</script>

<style scoped lang="scss">

  .card {
    width: 310px;
    overflow: hidden;
    border-radius: 2%;
    box-shadow: 1px 1px 30px rgba(195, 246, 200, 0.1);
    margin-bottom: 30px;
    margin-top: 35px;
    cursor: pointer;

    img {
      width: 100%;
      height: 190px;
      margin: 0;
    }

    .card-text {
      padding: 0px 15px;
    }

    h2 {
      font-weight: bold;
    }
  }


</style>