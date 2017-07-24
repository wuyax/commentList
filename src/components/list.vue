<template>
  <div class="col-md-8">
    <h3 class="reply">评论回复：</h3>
    <h2 v-show="components.length===0">暂无评论，点击左侧添加评论！！！</h2>
    <ul class="list-group">
      <item v-for="(component,index) in components" :component="component" :index="index" :remove="remove" :key="index"></item>
    </ul>
  </div>
</template>

<script>
import item from './item.vue';
export default {
  props: {
      components: {
            type: Array,
            required:true
      },
      remove: {
            type:Function,
            required:true
      }},

  components: {
      item
  }
}

</script>

<style>

</style>
