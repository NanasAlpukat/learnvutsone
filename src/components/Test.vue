<script setup lang="ts">
import { ref } from 'vue';
import type { Props } from '../config/items';


// props' fun take some data from parent to child
const _age = ref(0)
const props = defineProps<Props>()
console.log(props.btn_class);  


// emit's func callback data to parent
const emit = defineEmits<{(e:"changeItem",age:number):any}>();
const setItems = (data:number) =>{
  emit('changeItem',data)
}
</script>

<template>
  <h1 class="btn">My name is {{props.msg.nama}} my age is {{ props.msg.age }} years old</h1>
  <input class="border outline-purple-800" type="number" v-model="_age"/>
  <button class="t-btn" :class="props.btn_class"  type="submit" @click="setItems(_age)">Submit</button>
</template>
