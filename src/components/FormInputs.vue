<template>
  <div  class ="styleForm">
    <input v-on:keyup="inputChangeHandler" class ="styleInput" v-model="valueName" placeholder="Ваше имя" text-align="center">
    <input v-on:keyup="inputChangeHandler" class ="styleInput" v-model="valueComment" placeholder="Комментарий" text-align="center">
    <button @click="addComment" class ="styleButton">Add comment</button>
    <removed-comments/>
  </div>
</template>

<script>
export default {
  name: 'FormInputs',
  data: {
    valueName: "",
    valueComment: "",
  },
  components: {
    RemovedComments,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.styleInput {
    width: 100%;
    height: 30px;
    border-radius: 5px;
    border: 3px solid #6BCBB6;
    outline: none;
    transition: 0.5s;
    text-align: center;
    margin-bottom: 5%;
  }

  .styleButton{
    padding: 0;
    border: none;
    font: inherit;
    color: inherit;
    cursor: pointer;
    color: #ffffff;
    background-color: #6BCBB6;
    border-radius: 5px;
    outline: none;
    transition: 0.5s;
    width: 100%;
    height: 40px;
    justify-content: flex-end;
  }
</style>
