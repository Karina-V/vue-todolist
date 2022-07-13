<template>

    <div class="py-5 flex flex-col px-1.5">
        <h3 class="flex justify-center text-3xl text-center">~ Today I need to ~</h3>
        <form class="form-wrapper pt-5 flex-wrap">
            <div class="form-input my-1">
                <input v-model="todoText" class="input-col" ref="inputRef" placeholder="Add new todo..." autofocus />
            </div>
            <button type="submit" class="submit-btn my-1" @click.prevent="createTodo"><span
                    class="create-list">Add</span></button>
        </form>
    </div>

</template>

<script>

export default {
    data() {
        return {
            todoText: ''
        }
    },
    methods: {
        createTodo() {
            this.$emit('create-todo', this.todoText);
            this.todoText = '';
        },
    },
}

</script>

<style src="./ReceivingList.css">
</style>

