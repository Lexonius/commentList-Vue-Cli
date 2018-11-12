<template>
  <div class ="styleForm">
    <input class="styleInput" v-model="name" placeholder="Ваше имя">
    <input class ="styleInput" v-model="commentText" placeholder="Комментарий">
    <!-- по клику запускается addComment из methods -->
    <button @click="addComment" class ="styleButton">Add comment</button>
    
  </div>
</template>

<script>
// import RemovedComments from '../src/components/RemovedComments.vue'

export default {
  data() {
    return {
      name: '',
      commentText: ''
    }
  },
  methods: {
    addComment() {
      const now = new Date();
      //наше пользовательское событие onInputData, по которому создается объект
      this.$emit('onInputData', {
        avatar: "",
        name: this.name,
        comment: this.commentText,
        date: {
          weekDay: now.getDate(),
          month: now.getMonth(),
          year: now.getFullYear(),
          hour: now.getHours(),
          minutes: now.getMinutes()
        },
        id: Date.now(),
        remove: ""
      });
      this.name = '';
      this.commentText = '';
    }
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
    /* padding: 0;
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
    justify-content: flex-end; */
  }

  .styleForm {
      display: flex;
      flex-direction: column;
      /* width: 25%; */
    }

  
</style>
