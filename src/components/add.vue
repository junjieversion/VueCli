<template>
      <div class="col-md-4">
        <form class="form-horizontal">
          <div class="form-group">
            <label>用户名</label>
            <input v-model="name" type="text" class="form-control" placeholder="用户名">
          </div>
          <div class="form-group">
            <label>评论内容</label>
            <textarea v-model="comment" class="form-control" rows="6" placeholder="评论内容"></textarea>
          </div>
          <div class="form-group">
            <div class="col-sm-offset-2 col-sm-10">
              <button @click="add" type="button" class="btn btn-default pull-right">提交</button>
            </div>
          </div>
        </form>
      </div>
</template>

<script>
export default {
  props: {
    addComment:{
      type: Function,
      required: true
    }
  },
  data() {
    return {
      name: '',
      comment: ''
    }
  },
  methods: {
    add () {
      //收集数据
      let name = this.name.trim()
      let comment = this.comment.trim()
      //判断数据合法性
      if (!name || !comment ) {
        alert('请输入完整信息')
        return
      }
      //数据传输至APP组件
      let obj = {name, comment}
      this.addComment(obj)
      //清空用户数录数据
      this.name = ''
      this.comment = ''
    }
  }
}
</script>

<style scoped>

</style>
