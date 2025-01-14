<template>
  <input type="text" v-model="newElement">
  <button @click="sendElement">Add</button>
  <button @click="emit('cancel-element')">Cancel</button>
</template>

<script setup>
import { ref } from 'vue';
const emit = defineEmits(['new-element', 'cancel-element']);
let newElement = ref('');

function sendElement(undefined) {
  if (newElement.value != '') {
    emit('new-element', newElement.value);
    newElement.value = '';
  }
}
</script>

<style lang="scss" scoped></style>
