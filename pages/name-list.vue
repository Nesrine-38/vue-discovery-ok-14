<script lang="ts" setup>
import {ref} from 'vue';
const names= ref(['nesrine','alex','sarah','celia', 'xiaoyu','yasmine']);
const newName= ref('');


function addName() {
  names.value.push(newName.value);
}
</script>

<template>
  <div>
    <input type="text" v-model="newName" placeholder="type a name ...">
    <button @click="addName()">Add</button>
    <ul>
      <li v-for="item of names">{{ item }}</li>
    </ul>
  </div>
</template>

<style scoped></style>
