<template>
  <li class="list-group-item">
    <div class="handle">
      <a href="javascript:;" @click="rm">删除</a>
    </div>
    <p class="user"><span >{{component.username}}</span><span>说:</span></p>
    <p class="centence">{{component.comment}}</p>
  </li>
</template>

<script>
  export default {
    props: ['component','index','remove'],
    methods: {
        rm () {
            if(confirm(`你确定要删除${this.component.username}的评论吗？`)){
              this.remove(this.index);
            }

        }
    }
  }
</script>

<style>

</style>
