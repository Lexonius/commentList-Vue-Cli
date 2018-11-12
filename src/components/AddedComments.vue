<template>
  <div class ="styleCommentWrap">
    <div class ="styleCommentBlock">
      <ul v-if="addedComments.length" class ="styleList">
        <added-comment v-for="item in addedComments" 
          :key="item.id" :comment="item"
          @onRemoveComment="removeComment"
          :added-comments="addedComments"/>
      </ul>
      <div v-else>Комментарии отсутствуют</div>
    </div>
  </div>
</template>

<script>
import AddedComment from "./AddedComment.vue";

export default {
  name: "addedComments",
  props: ["added-comments"],
  components: {
    AddedComment
  },
  methods: {
    removeComment(id) {
      this.$emit('removeCommentHandler', id);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.styleCommentWrap {
  border: 3px solid #6bcbb6;
  border-radius: 5px;

}

.styleCommentBlock {
  width: 100%;
  height: 970px;
}

.styleList {
  list-style: none;
  margin: 0;
  padding: 0;
}

.styleButton {
  padding: 0;
  border: none;
  font: inherit;
  color: inherit;
  cursor: pointer;
  color: #ffffff;
  background-color: #6bcbb6;
  border-radius: 5px;
  outline: none;
  transition: 0.5s;
  width: 100%;
  height: 40px;
  justify-content: flex-end;
  margin-top: 1%;
}
</style>