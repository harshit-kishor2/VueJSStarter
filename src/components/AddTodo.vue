<template>
  <div>
      <form @submit="submitHandle">
          <input type="text" name="title" v-model="title" placeholder="Enter title....">
          <input type="submit" value="Submit" class="btn">
      </form>
  </div>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';
export default {
    name:"Addtodo",
    data(){
        return{
            title:''
        }
    },
    methods:{
        submitHandle(e){
            e.preventDefault()
            //construnt new todo then emit to parent
            const newTodo={
                id:uuidv4(),
                title:this.title,
                completed :false
            }
            //send up to parent
            this.$emit('submit-handle',newTodo)
            this.title=''
        }
    }

}
</script>

<style scoped>
form{
    display: flex;
}
input[type='text']{
    flex: 10;
    padding: 5px;
}
input[type='submit']{
    flex: 2;
    background: rgb(127, 127, 223);
}

</style>