<template>
    <div class ="historyBlock">
        <ul v-if="removedComments.length" class ="styleRemovedList">
            <removed-comment v-for="elem in removedComments" 
            :key="elem.id" :removeComment="elem"
            @onAddReversesComment="addReverseComment"
            :removed-comments='removedComments'
            />
        </ul>
    <div v-else>Изменений нет</div>
    </div>
</template>

<script>
import RemovedComment from './RemovedComment.vue'

export default {
  name: 'RemovedComments',
  props: ['removed-comments'],
  components: {
    RemovedComment,
  },
  methods: {
    addReverseComment(id) {
      this.$emit('addReverseCommentHandler', id);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.historyBlock{
    border: 3px solid rgb(107, 203, 182);
    margin-top: 5%;
    height: 80%;
    border-radius: 5px;
  }

.styleRemovedList {
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>