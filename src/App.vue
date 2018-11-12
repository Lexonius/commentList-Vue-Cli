<template>
  <div id="app">
    <!-- кастомное событие на инпуты -->
    <div class="app__block--left">
      <form-inputs @onInputData="addCommentHandler" />
      <removed-comments :removed-comments="removedComments" @addReverseCommentHandler="addReverseCommentHandler"/>
    </div>
    <div class="app__block--rigth">
      <!-- прокидываем в наш компонент added-comments наш массив addedComments -->
      <added-comments :added-comments="addedComments" @removeCommentHandler="removeCommentHandler"/>
      <add-button-comment :add-button-comment="addedComments, removedComments" />
    </div>
  </div>
</template>

<script>
import FormInputs from './components/FormInputs.vue'
import RemovedComments from './components/RemovedComments.vue'
// import RemovedComment from './components/RemovedComment.vue'
import AddedComments from './components/AddedComments.vue'
// import AddedComment from './components/AddedComment.vue'
import AddButtonComment from './components/AddButtonComment.vue'

export default {
  name: 'app',
  components: {
    'form-inputs': FormInputs,
    // RemovedComments,
    'added-comments': AddedComments,
    'removed-comments': RemovedComments,
    'add-button-comment': AddButtonComment
  },
  data() {
    return {
      //массив с добавленными комментариями
      addedComments: [],
      //массив с удаленными комментариями
      removedComments: []
    }
  },
  methods: {
    addCommentHandler(comment) {
      this.addedComments.push(comment);
    },

    removeCommentHandler(id){
      const nowRemove = new Date();
      const commentIndex = this.addedComments.findIndex(
        a => a.id === Number(id)
      );
      console.log(commentIndex);
      let removeComment = this.addedComments.splice (commentIndex, 1);
      this.removedComments.push(removeComment[0]);
    },

    addReverseCommentHandler(id){
      const nowRemove = new Date();
      const commentIndex = this.removedComments.findIndex(
        a => a.id === Number(id)
      );
      console.log(commentIndex);
      let addReverseComment = this.removedComments.splice (commentIndex, 1);
      this.addedComments.push(addReverseComment[0]);
    }
  }
}

</script>

<style>

#app {
  outline: none;
  display: flex;
  flex-direction: row;
  height: 960px;
}

.app__block--left {
  width: 25%;
}
.app__block--rigth {
  width: 75%;
  margin-left: 1%;
}


</style>
