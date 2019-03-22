<template>
      <div>
        <header class="site-header jumbotron">
          <div class="container">
            <div class="row">
              <div class="col-xs-12">
                <h1>请发表对React的评论</h1>
              </div>
            </div>
          </div>
        </header>
        <div class="container">
          <add :addComment="addComment"></add>
          <list :comments="comments" :delComment="delComment"></list>
        </div>
      </div>
 </template>

<script>
  import add from './add.vue'
  import list from './list.vue'
  export default {
    components: {
      add, list
    },
    data() {
      return{
        comments: [
          {name:'俊杰', comment: '我太帅了'},
          {name:'文波', comment: '我是大神'}
        ]
      }
    },
    methods: {
      addComment(obj) {
        this.comments.unshift(obj)
      },
      delComment(index) {
        this.comments.splice(index, 1)
      }
    }
  }
</script>

<style>
  .reply {
    margin-top: 0px;
  }

  li {
    transition: .5s;
    overflow: hidden;
  }

  .handle {
    width: 40px;
    border: 1px solid #ccc;
    background: #fff;
    position: absolute;
    right: 10px;
    top: 1px;
    text-align: center;
  }

  .handle a {
    display: block;
    text-decoration: none;
  }

  .list-group-item .centence {
    padding: 0px 50px;
  }

  .user {
    font-size: 22px;
  }
</style>
