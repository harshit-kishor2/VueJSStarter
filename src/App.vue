<template>
  <div id="app">
    <Header></Header>
    <AddTodo v-on:submit-handle="addHandle"/>
    <div class="empty" v-if="todos.length==0"> Your Cart is Empty...</div>
   <Todos v-bind:todos="todos" v-on:del-handle="deleteHandle"></Todos> 
   <Footer></Footer>
  </div>
</template>

<script>

 import Todos from "./components/Todos";
 import AddTodo from "./components/AddTodo";
 import Header from "./components/layout/Header";
 import Footer from "./components/layout/Footer";
export default {
 
  name: 'App',
  components: {
    Todos,
    Header,
    Footer,
    AddTodo
  },
  data(){
    return{
      todos:[
        {
        id:1,
        title:'todos1',
        completed:true
      },
      {
        id:2,
        title:'todos2',
        completed:true
      },{
        id:3,
        title:'todos3',
        completed:false
      },{
        id:4,
        title:'todos4',
        completed:true
      },
      {
        id:5,
        title:'todos5',
        completed:true
      },
      {
        id:6,
        title:'todos6',
        completed:false
      },{
        id:7,
        title:'todos7',
        completed:true
      },{
        id:8,
        title:'todos8',
        completed:false
      }
      ]
    }
  }
,
methods:{
deleteHandle(id){
  this.todos=this.todos.filter(todo=>todo.id!=id)
},
addHandle(newTodo){
  this.todos=[...this.todos,newTodo];
}
  },

}
</script>

<style>
*{
  margin: 0;
  padding: 0;
}
body{
  font-family: Arial, Helvetica, sans-serif;
  line-height: 1.4;
}
.empty{
  text-align: center;
}

</style>
