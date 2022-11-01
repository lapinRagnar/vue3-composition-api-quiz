<script setup>

  import q from '@/data/quize.json'
  import { ref, watch } from 'vue'
  import Card from '@/components/Card.vue'

  const quizes = ref(q)
  const search = ref('')

  watch(search, () => {
    quizes.value = q.filter(quiz => quiz.name.toLowerCase().includes(search.value.toLowerCase()))
  })

</script>

<template>
  
  <header>
    <h1>Quizes</h1>
    <input v-model.trim="search" type="text" placeholder="rechercher...">

    <div class="options-container">

      <Card v-for="quiz in quizes" :key="quiz.id" :quiz="quiz" />

    </div>

  </header>
  
</template>

<style scoped lang="scss">

  header {
    margin-bottom: 10px;
    margin-top: 30px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;

    h1 {
      font-weight: bold;
      margin-right: 30px;
      color: rgb(95, 22, 22);
      font-size: 50px;
    }

    input {
      border: none;
      background-color: rgba(128, 128, 128, 0.1);
      width: 300px;
      height: 32px;
      border-radius: 5px;
      padding: 10px;
      &:focus {
        outline: none;
        border: 1px solid greenyellow;
      }
    }

    .options-container{
      display: flex;
      flex-wrap: wrap;
      margin-top: 4px;
      gap: 20px;

    }
  }
  

</style>