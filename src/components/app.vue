<template>
    <div>
      <header class="site-header jumbotron">
        <div class="container">
          <div class="row">
            <div class="col-xs-12">
              <h1>请发表对Vue的评论</h1>
            </div>
          </div>
        </div>
      </header>
      <div class="container">
        <add :add="add"></add>
        <list :components="components" :remove="remove"></list>
      </div>
    </div>
</template>

<script>
import add from './addc.vue';
import list from './list.vue';
export default{
    data () {
        return{
            components:[
              {username:'tom',comment:'hello shanghai'},
              {username:'jack',comment:'hello beijing'}
            ]
        }
    },
  components: {
        add,
        list
  },
  methods: {
        add (components) {
            this.components.unshift(components)

        },
        remove (index) {
            this.components.splice(index,1)
        }
  }
}
</script>

<style>

</style>
