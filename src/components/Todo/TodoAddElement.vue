<template>
  <li>
    <button @click="addElement">+</button>
  </li>
</template>

<script setup>
const emit = defineEmits(['add-element']);

function addElement() {
  emit('add-element');
}

</script>

<style lang="scss" scoped></style>
