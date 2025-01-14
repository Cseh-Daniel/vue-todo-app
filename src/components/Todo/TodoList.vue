<template>
  <div>
    <ul>

      <TodoElement v-for="(element, i) in elements" :key="i" :element="{ text: element, id: i }" />
      <TodoAddElement @add-element="addElement" :hidden="isNewElementActive" />
      <li :hidden="!isNewElementActive">
        <TodoNewElement @new-element="newElement" @cancel-element="cancelElement" />
      </li>
    </ul>
  </div>
</template>

<script setup>
import TodoElement from '@/components/Todo/TodoElement.vue';
import { defineProps } from 'vue'
import TodoAddElement from './TodoAddElement.vue';
import TodoNewElement from './TodoNewElement.vue';
import { ref } from 'vue';

const props = defineProps({
  elements: {
    type: Array,
    required: true
  }
})

let isNewElementActive = ref(false);

let elementList = ref(props.elements);

function addElement() {
  switchHidden();
}

function switchHidden() {
  isNewElementActive.value = !isNewElementActive.value;
}

function newElement(newElement) {
  if (newElement != undefined && newElement != '') {
    switchHidden();
    elementList.value.push(newElement);
  } else if (newElement == undefined && newElement != '') {
    switchHidden();
  }
}

function cancelElement() {
  isNewElementActive.value = false;
}

</script>

<style lang="scss" scoped></style>
