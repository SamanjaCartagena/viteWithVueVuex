<template>
  <div>
    Home
  </div>
  <p>Name in store is {{name}}</p>

  <input v-model="newName" type="text"/>

  <button @click="saveName">Submit</button>
</template>

<script setup>

import { useStore } from 'vuex'
import { computed, ref } from 'vue'
import { useRouter } from 'vue-router'
const store = useStore()
const router = useRouter()
const name = computed(() => {
    return store.state.user.name
})

const newName = ref('')

function saveName(){
    store.dispatch('saveName', newName.value)
    newName.value=''
    router.push('/about')
}

</script>

<style>

</style>