<template>
<div class="todo">
<h2>MY TODOLIST</h2>
<todo-input @additem="addTodoItem" @clearAll="clearAll"></todo-input>
<todo-list :todoItem="todoItem" @reDel="removeDel"></todo-list>
<todo-footer>vvv</todo-footer>
 </div> 
</template>

<script>
import TodoFooter from './components/TodoFooter.vue'
import TodoInput from './components/TodoInput.vue'
import TodoList from './components/TodoList.vue'
export default {
  components: { TodoInput, TodoList, TodoFooter },
  data(){
    return{
      todoItem:[]
    }
  },
  created(){
for(let i=0;i<localStorage.length;i++){
  this.todoItem.push(localStorage.key(i))
}
  },
  methods:{
    addTodoItem(item){
      this.todoItem.push(item);
      localStorage.setItem(item,item)
    },
    removeDel(num,item){
      this.todoItem.splice(num,1);
      localStorage.removeItem(item)

    },
    clearAll(){
      this.todoItem=[];
      localStorage.clear();
    }
  }
  

}
</script>

<style>
@import url("./assets/style.css");
body{_width: 100%;padding: 5%;}
.todo{width: 70%;background: rgb(30, 62, 150);padding: 10%;
border-radius: 10px;margin: 0 auto;}
 h2{ color: white;margin-bottom: 50px;font-size:3.5vw;

 }
</style>