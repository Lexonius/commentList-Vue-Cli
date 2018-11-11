<template>
  <div id="app">
    <form-inputs/>
    <removed-comments/>
    <!-- <removed-comment/> -->
    <added-comments/>
    <!-- <added-comment/> -->
    <add-button-comment/>
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
    FormInputs,
    RemovedComments,
    AddedComments,
    AddButtonComment
  }
}
</script>

// <style>
// .styleBlock {
//   outline: none;
//   display: flex;
//   flex-direction: row;
//   height: 960px;
// }
// </style>
