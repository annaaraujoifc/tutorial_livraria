<script setup>
import { onMounted, ref } from 'vue'
import { useBooksStore } from '../../stores/books'
const props = defineProps(['id'])
const booksStore = useBooksStore()
const currentBook = ref({})

onMounted(() => {
    currentBook.value = booksStore.getBookById(props.id)
})
</script>

<template>
    <h1>Detalhes do livro: {{ id }}</h1>
    <p>Este é o conteúdo da página de detalhes do livro</p>
    <div v-if="currentBook.id">
        <p>Titulo: {{ currentBook.title }}</p>
        <img :src="currentBook.cover" alt="Capa do livro">
    </div>
    <div v-else>
        <p>Livro não encontrado</p>
    </div>
</template>