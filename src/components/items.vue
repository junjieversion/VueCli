<template>
  <li class="list-group-item">
    <div class="handle">
      <a @click="del" href="javascript:;">删除</a>
    </div>
    <p class="user"><span >{{items.name}}</span><span> 说: </span></p>
    <p class="centence">{{ items.comment }}!</p>
  </li>
</template>

<script>
  export default {
    props: {
      items: {
        type: Object
      },
      delComment: {
        type: Function
      }
    },
    methods: {
      del () {
        if (confirm(`你确定要删除${this.items.name}的评论吗？`)){
          this.delComment(this.index)
        }
      }
    }
  }
</script>

<style scoped>

</style>
