<template>
    <div class ="historyBlock">
        <ul v-if="removeComments.length" class ="styleRemovedList">
                <removed-comment/>
        </ul>
    <div v-else>Изменений нет</div>
    </div>
</template>

<script>
export default {
  name: 'RemovedComments',
  data: {
    removeComments: [],
  },
  components: {
    RemovedComment,
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.historyBlock{
    border: 3px solid rgb(107, 203, 182);
    margin-top: 5%;
    height: 100%;
    border-radius: 5px;
  }

.styleRemovedList {
    list-style: none;
    margin: 0;
    padding: 0;
  }
</style>