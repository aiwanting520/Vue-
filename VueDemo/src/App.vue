<template>
  <div class="todo-container">
    <div class="todo-wrap">
      <TodoHeader :addTodo="addTodo"/>
      <TodoMain :todos="todos" :deleteTodo="deleteTodo"/>
      <TodoFooter/>
    </div>
  </div>


</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  data () {
    return {
      todos: [
        {title:'吃饭',complete:false},
        {title:'睡觉',complete:true},
        {title:'打豆豆',complete:false},
      ]
    }
  },
  methods:{
      //更新数据的方法
      addTodo(todo){
          //将数据添加到数组的头部，this是vm
          this.todos.unshift(todo);
      },
    deleteTodo(index){
          this.todos.splice(index,1);
    }
  },
  components: {
    TodoHeader:Header,
    TodoMain:Main,
    TodoFooter:Footer,
  }
}
</script>

<style>
  .todo-container {
    width: 600px;
    margin: 0 auto;
  }
  .todo-container .todo-wrap {
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
  }
</style>
