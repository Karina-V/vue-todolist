<template>
    <div class="flex justify-center items-center px-1.5 flex-wrap">
        <div class="py-8">
            <HeadingImg class="img-style" />
        </div>
        <div class="title text-slate-50 font-semibold">To-Do List</div>
    </div>
</template>

<script>
import HeadingImg from "./NoteImg.vue"

export default {
    components: {
        HeadingImg,
    }
}
</script>

<style src="./Heading.css">
</style>