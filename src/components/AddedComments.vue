<template>
    <div class ="styleCommentWrap">
        <div class ="styleCommentBlock">
          <ul v-if="comments.length" class ="styleList">
              <added-comment/>
            </ul>
            <div v-else>Комментарии отсутствуют</div>
        </div>
        <button @click="saveComment" class ="styleButton">save comment</button> 
      </div>
</template>

<script>
export default {
  name: 'addedComments',
  data: {
   comments: [],
  },
  components: {
    AddedComment,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .styleCommentWrap {
    width: 75%;
    border: 3px solid #6BCBB6;
    border-radius: 5px;
    margin-left: 1%;
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