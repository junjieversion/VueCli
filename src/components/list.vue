<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 style='display: none'>暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
      <items v-for="(items, index) in comments" :items="items" :key="index" :index="index" :delComment="delComment"></items>
    </ul>
  </div>
</template>

<script>
  import items from './items.vue'
  export default {
    props: {
      comments: {
        type: Array
      },
      delComment: {
        type: Function
      }

    },
    components: { items }
  }
</script>

<style scoped>

</style>
