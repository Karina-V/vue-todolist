<template>

    <div class="py-5">
        <div v-if="todoItems.length > 0">
            <div v-for="todo in todoItems" :key="todo.id" class=" w-9/12 p-3 my-4 border-0 border-l-4 border-b-4 border-orange-500 rounded-lg flex
        justify-between items-center shadow-2xl mx-auto">
                <label for="checkbox">
                    <input type="checkbox" class="accent-orange-500 cursor-pointer" :checked="todo.done"
                        @click="onTaskDoneChanged($event.target.checked, todo)">
                </label>
                <p class="cursor-pointer text-black-400 overflow-hidden w-full h-6 relative pl-2.5 text-left">
                    {{ todo.text }}
                </p>
                <div>
                    <i @click="$emit('remove', todo)"
                        class=" fa-solid fa-trash-can text-red-500 mr-4 cursor-pointer"></i>
                </div>
            </div>
        </div>

        <div v-else class="py-5 text-grey-400 flex justify-center items-center">

            &#10003; Congrat, you have no more list to do
        </div>
    </div>

</template>

<script >

export default {
    props: ['todoItems'],
    methods: {
        onTaskDoneChanged(checked, todo) {
            todo.done = checked
            this.$emit('todo-changed', todo)
        }
    }
}
</script> 