<template>
    <div>
        <h2>{{ name }}</h2>
        <button @click="setName">Change Name</button>

        <h2>{{ count }}</h2>
        <button @click="incrementCount">IncrementCount</button>

        <h2>{{ first }} {{ last }}</h2>
        <button @click="changeHero">Change Hero</button>
    </div>
</template>

<script>
    import {ref, reactive, toRefs} from 'vue'
    export default {
        name: 'MethodsComponent',
        setup(){
            const count = ref(0)
            const state = reactive({
                first:'Bruce',
                last: 'Wayne'
            })

            function incrementCount(){
                count.value++
            }

            function changeHero(){
                state.first = 'Clark'
                state.last = 'Kent'
            }
            return {
                count,
                incrementCount,
                ...toRefs(state),
                changeHero
            }
        },
        data(){
            return{
                name : 'Sagar'
            }
        },
        methods:{
            setName(){
                this.name = 'Codevolution'
            }
        }
    }
</script>

<style scoped>

</style>