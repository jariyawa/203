<script setup>
import { ref, computed } from 'vue'
const myNotes = ref([])
const newNote = ref('')
const addNote = () => myNotes.value.push(newNote.value)
</script>



<template>
    <div v-show="myNotes != ''">
        Filter Note:
        <input type="text" />
        <ul>
            <li v-for="(myNote, index) in myNotes" :key="index">{{ myNote }}</li>
        </ul>
    </div>New Note:
    <input type="text" class="border-2 " v-model="newNote" />

    <button @click="addNote" class="border-2 cursor-pointer ">Add Note</button>
</template>



<style></style>