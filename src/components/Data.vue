<template>
    <div>
        <h2>Options - {{o_firstName}}</h2>
        <h2>Options - {{o_firstName}} {{o_lastName}} {{o_heroName}}</h2>

        <h2>Composition - {{c_firstName}} </h2>
        <h2>Composition - {{ greet }}</h2>

        <h2>Composition - {{o_firstName}} {{o_lastName}} {{o_heroName}}</h2>
        <h2>Composition - {{ greetHero }}</h2>

        <h2>Composition {{state.firstName}} - {{state.lastName}} - {{state.herotName}}</h2>
        <h2>Composition {{reactiveGreetHero}} </h2>




    </div>
</template>

<script>

import { ref, reactive } from 'vue'

export default {
    name: 'Data',
    setup(){
        const c_firstName = ref('Clarck')
        const c_lastName = ref('Kent')
        const c_herotName = ref('Superman')

        const greet = `Hello ${c_firstName.value}`
        const greetHero = `Hello ${c_firstName.value} ${c_lastName.value} a.k.a ${c_herotName.value}`

        const state = reactive({
            firstName: 'princes',
            lastName: 'diana',
            herotName: 'wonder woman',
        })

        const reactiveGreetHero = `hello ${state.firstName} - ${state.lastName} - ${state.herotName}`

        return{
            c_firstName,
            c_lastName,
            c_herotName,
            greet,
            greetHero,
            state,
            reactiveGreetHero

        }
    },
    data(){
        return{
            o_firstName: 'Bruce',
            o_lastName: 'Wayne',
            o_heroName: 'Betman',

        }
    },
}
</script>

<style scoped>

</style>