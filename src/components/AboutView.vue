<template>
  <div>
    <h1>About {{name}}</h1>
  </div>
</template>

<script setup>
import {computed} from 'vue'
import { useStore } from 'vuex'
const store = useStore()

const name = computed(() =>{
    return store.state.user.name
})
</script>

<style>

</style>