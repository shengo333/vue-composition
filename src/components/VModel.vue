<template>
  <div>
      <!-------option API ------>
      <input type="text" placeholder="First Name" v-model="fName">
      <input type="text" placeholder="last Name" v-model="lName">

      <input type="text" placeholder="Hero Name" v-model="heroName">
      <input type="text" placeholder="First Name" v-model="firstName">
      <input type="text" placeholder="last Name" v-model="lastName">
  </div>
</template>

<script>

import {ref, reactive, toRefs, toRef} from 'vue'
export default {
    name: 'VModel',
    setup(){
        const heroName = ref('')
        const state = reactive({
            firstName: '',
            lastName: ''
        })
        return{
            heroName,
            ...toRefs(state)
        }
    },
    data(){
        return{
            fName: '',
            lName: '',
        }
    }
}

</script>

<style>

</style>