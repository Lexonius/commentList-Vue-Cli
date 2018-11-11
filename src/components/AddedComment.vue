<template>
<li v-for="comment in comments" :key="comment.id" class ="styleComment">
      <img src="./img/usuario.jpeg" class ="styleAvatar"> 
    <div class ="styleCommentCenter">
      <div class ="styleCommentCenterTop">
        <div >
          {{ comment.name }}
        </div>
          <div>
            {{ comment.date.weekDay }}.
            {{ comment.date.month }}.
            {{ comment.date.year }}
            {{ comment.date.hour }}:
            {{ comment.date.minutes }}
          </div>
      </div>
      <div class="styleCommentCenterBottom">
        {{ comment.comment }}
      </div>
    </div>
    <div class ="styleCommentRight">
      <img src="./img/remove.png" @click="removeComment(comment.id)" class ="styleButtonRemove">
    </div>
</li>
</template>

<script>
export default {
  name: 'RemovedComment',
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