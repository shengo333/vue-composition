<template>
  <div>
      <!-------option API ------>
      <input type="text" placeholder="Name" v-model="name">

      <input type="text" placeholder="First Name" v-model="firstName">
      <input type="text" placeholder="Last Name" v-model="lastName">


  </div>
</template>

<script>


import {ref, watch} from 'vue'
export default {
    name: 'Watch',
    setup(){
        const firstName = ref('')
        const lastName = ref('wayne')

        watch ([firstName,lastName], (newValues, oldValues) => {
            console.log('First Name old value', oldValues[0])
            console.log('First Name new value', newValues[0])
            console.log('Last Name old value', oldValues[1])
            console.log('Last Name new value', newValues[1])
        }, {
            immediate: true
        })
        return{
            firstName,
            lastName
        }
    },
    data(){
        return{
            name: '',
            
        }
    },
    watch: {
        name(newValue, oldValue){
            console.log('old value', oldValue)
            console.log('new value', newValue)
        },
    },
}

</script>

<style>

</style>