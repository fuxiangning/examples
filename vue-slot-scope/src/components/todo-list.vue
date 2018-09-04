<template>
  <ul>
    <li v-for="item in todoList" v-bind:key="item.id">
      <slot v-bind:itemValue = "item" >
         {{ item.test }} 
      </slot>
    </li>
  </ul>
</template>

<script>
export default {
  name: 'todoList',
  props: {
    todos: Array
  },
  data(){
    return {
      todoList:this.todos
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display:block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
