<template>
  <div class="col-md-4">
    <form class="form-horizontal">
      <div class="form-group">
        <label>用户名</label>
        <input type="text" class="form-control" placeholder="用户名" v-model="username">
      </div>
      <div class="form-group">
        <label>评论内容</label>
        <textarea class="form-control" rows="6" placeholder="评论内容" v-model="comment"></textarea>
      </div>
      <div class="form-group">
        <div class="col-sm-offset-2 col-sm-10">
          <button type="button" class="btn btn-default pull-right" @click="submit">提交</button>
        </div>
      </div>
    </form>
  </div>
</template>

<script>
  export default {
      props: {add: {
          type:Function,
          required:true
      }},
      data () {
          return {
              username: '',
              comment: ''
          }
      },
      methods: {
          submit () {
              let {username,comment}=this;
              if(!username.trim() || !comment.trim()){
                  return;
              };
              username = username.trim();
              comment = comment.trim();
              let components = {username,comment}
              this.add(components);

              this.username = '';
              this.comment = '';
          }
      }
  }
</script>

<style>

</style>
