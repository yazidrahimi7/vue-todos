<template>
    <div class="row">
        <app-todo v-for="(i, j) in list" :key="i" @click.native="deleteList(j)"> {{ i }} </app-todo>
    </div>
</template>

<script>
    import Todo from './Todo.vue'

    export default {
       props: ['list'],
       components: {
           appTodo: Todo,
       },
       methods: {
           deleteList(j) {
               this.$emit('emitDelete', j )
           }
       },
    }
</script>

<style scoped>

</style>