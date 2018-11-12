<template>
<li class ="styleRemovedComment">
    <div class ="styleRemovedCommentCenter">
      <div class ="styleRemovedCommentCenterTop">
        <div>
          {{ removeComment.name }}
        </div>
          <div>
            {{ removeComment.date.weekDay }}.
            {{ removeComment.date.month }}.
            {{ removeComment.date.year }}
            {{ removeComment.date.hour }}:
            {{ removeComment.date.minutes }}
          </div>
      </div>
      <div class="styleCommentCenterBottom">
        {{ removeComment.comment }}
      </div>
    </div>
    <div class ="styleCommentRight">
      <img src="../assets/add.png" @click="addReverseComment(removeComment.id)" class ="styleButtonRemove">
    </div>
</li>    
</template>

<script>
export default {
  name: 'RemovedComment',
  props: ['removeComment', 'removed-comments'],
  methods:{
    addReverseComment(removeCommentId){
      console.log(removeCommentId);
      
      this.$emit('onAddReversesComment', removeCommentId);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
  .styleRemovedCommentCenterTop {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
  }

  .styleRemovedCommentCenter {
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    width: 80%;
  }

    .styleCommentRight {
    display: flex;
    align-items: center;
  }

  .styleButtonRemove {
    height: 20px;
  }

    .styleRemovedComment {
    display: flex;
    height: 100px;
    justify-content: space-between;
    padding: 1%;
    border-bottom-style: solid;
    border-bottom-width: 2px;
    border-bottom-color: #6BCBB6;
  }

    .styleAvatar {
    width: 100px;
  }

</style>