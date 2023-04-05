<template>
    <div>
        <h3>Parent Component {{ name }}</h3>
        <h3>Parent Component count {{ count }}</h3>
        <h3>Parent Component hero {{ firstName }} {{ lastName }}</h3>
        <ChildA/>
    </div>
</template>

<script>
    import ChildA from './ChildA.vue';
    import {provide, ref, reactive, toRefs} from 'vue'
    export default {
        components:{ChildA},
        name:'ProvideInject',
        setup(){
            provide('c_userName','Chopra')

            const count = ref(0)
            const state = reactive({
                firstName:'Bruce',
                lastName:'Wayne'
            })

            provide('c_count',count)
            provide('c_hero',state)

            return{
                count,
                ...toRefs(state)
            }
        },
        data(){
            return{
                name: 'Sagar'
            }
        },
        provide(){
            return{
                userName: this.name
            }
        }
    }
</script>

<style scoped>

</style>