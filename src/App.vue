<template>
  <div class="container">
    <header>
      <h1>Quizes</h1>
      <input type="text" placeholder="rechercher...">
      <div class="options-container">
        <div class="card">
          <img src="https://realitatea.md/wp-content/uploads/2021/09/matematica.png" alt="">
          <div class="card-text">
            <h2>Math</h2>
            <p>15 questions...</p>
          </div>
        </div>
      </div>
    </header>
  </div>
</template>

<style scoped lang="scss">

  .container {
    max-width: 1000px;
    /* margin: 0 auto; */
    height: 100vh;
    width: 100vw;
    display: flex;
    align-items: start;
    justify-content: center;

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


      }
    }
  }

</style>