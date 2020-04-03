<template>
    <div class="todos">
        <h2>Todo</h2>
        <div 
            class="todo"
            v-for="todo in todos"
            v-bind:key="todo.id"
            v-bind:class="{'is-complete':todo.completed}">
            <input type="checkbox" @click="todo.completed = !todo.completed">
            {{todo.title}}
        </div>   
    </div>
</template>

<script>
export default {
    name: "Todos",
    props: ["todos"]
}
</script>

<style scoped>
.todo {
    background-color: cornflowerblue;
    padding: 5px 10px;
    color: #fefefe;
    border-bottom: 1px solid #fefefe
}
.is-complete {
    text-decoration: line-through
}
</style>