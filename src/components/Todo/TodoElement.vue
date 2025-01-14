<template>
  <li>
    <input type="checkbox" name="" :id="$props.element.id" />
    {{ $props.element.text }}
  </li>
</template>

<script setup>
import { defineProps } from 'vue'
defineProps({
  element: {
    type: Object,
    required: true
  }
})
</script>

<style lang="scss" scoped></style>
