<script lang="ts" setup>
import { ref } from 'vue'
import { Dog } from '../entities';
const dog = ref<Dog>({ name: '', breed:'', birthdate: '' }); 
const emit = defineEmits (['submitted']);


function handleSubmit(){
  emit('submitted',dog.value);
}
</script>

<template>
  <div>
    <form @submit.prevent="handleSubmit">
      <label for="name">Name:</label>
    <input type="text" id="name" v-model="dog.name" placeholder="Name of the dog">
    <label for="Breed">Breed</label>
    <input type="text" id="Breed" v-model="dog.breed" placeholder="her breed">
    <label for="Brirthdate"></label>
    <input type="Date"  id="Brirthdate" v-model="dog.birthdate" placeholder="the birthdate of the dog">

    <button type="submit">Save</button>
  </form>
  </div>
</template>

<style scoped></style>
