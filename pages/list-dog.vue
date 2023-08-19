
<script lang="ts" setup>
import { useFetch } from 'nuxt/app';
import{ Dog } from 'entities'
import { METHODS } from 'http';
const {data, refresh} = await useFetch<Dog[]>('http://localhost:8000/api/dog');


async function addDog(dog:Dog) {
    await $fetch ('http://localhost:8000/api/dog',{
        method:'POST',
        body:dog
    });
    refresh();
}

</script>

<template>
<FormDog @submit-dog="addDog($event)"></FormDog>
<DogItem v-for="item of data" :dog="item"></DogItem>
</template>

<style scoped></style>
