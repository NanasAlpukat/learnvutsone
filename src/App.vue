<script setup lang="ts">
import Test from './components/Test.vue'
import { reactive } from 'vue';


const data : Biodata = reactive({nama:'annas',age: 20})
const setItem = (age:number) =>{
  data.age = age
}
</script>

<template>
  <div>
    <Test btn_class="t-btn-success" :msg="data"  @change-item="setItem"/>
  </div>
</template>
