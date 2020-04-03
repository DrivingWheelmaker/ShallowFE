<template>
    <form @submit.prevent="submit">
        <input type="text" placeholder="Add Todo" v-model="title">
        <input type="submit" value="Add">
    </form>
</template>

<script>
import { v4 as uuidv4 } from 'uuid';

export default {
    name: "AddTodo",
    data (){
        return{
            title: ""
        }
    },
    methods: {
        submit(){
            let todo = {
                id: uuidv4(),
                title: this.title,
                completed: false,
            };
            
            this.title= "" ;
            this.$emit('add-todo',todo);
        }
    }
}
</script>

<style scoped>
form {
    display: flex;
}
input[type="text"] {
    flex: 11;
    border: 1px solid #cccccc;
    padding: 4px;
}
input[type="submit"]{
    flex: 1;
    border: 1px solid rgb(162, 191, 247);
    background-color: cornflowerblue;
    color: #fefefe;
}
</style>