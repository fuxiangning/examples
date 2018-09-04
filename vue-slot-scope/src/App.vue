<template>
  <div id="app">
   <h2>之前组件调用</h2>
   <todo-list v-bind:todos="todosBefore" ></todo-list>
    <hr>

    <h2>之后组件调用</h2>
    <todo-list v-bind:todos="todosAfter">
      <template slot-scope="slotProps">
        <div style="background:red; border-bottom:2px solid blue;">
          {{slotProps.itemValue}}
        </div>
        <span v-if="slotProps.itemValue.isComplete">✓</span>
        {{ slotProps.itemValue.test }}
      </template>

    </todo-list>

  </div>
</template>

<script>
import todoList from './components/todo-list.vue'

export default {
  name: 'app',
  data:function(){
    return {
      todosBefore:[
        {
          test:'询问时间',
          id:12312313123
        },
        {
          test:'代办1',
          id:123123123423423
        },
        {
          test:'爱你地方年底见覅',
          id:12312313123234234
        },
        {
          test:'时间2',
          id:1231231312323333
        },
        {
          test:'师生情是行情',
          id:12313333333
        }
      ],
      todosAfter:[
        {
          test:'询问时间',
          isComplete:true,
          id:12312313123
        },
        {
          test:'代办1',
          isComplete:false,
          id:123123123423423
        },
        {
          test:'爱你地方年底见覅',
          isComplete:false,
          id:12312313123234234
        },
        {
          test:'时间2',
          isComplete:true,
          id:1231231312323333
        },
        {
          test:'师生情是行情',
          isComplete:true,
          id:12313333333
        }
      ],

    }
  },
  components: {
    todoList
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
