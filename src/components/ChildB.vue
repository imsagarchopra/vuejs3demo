<template>
    <div>
        <h2>Child Component B</h2>
        <h3> Child Component B username - {{ userName }}</h3>
        <h3> Child Component B composition username - {{ childUserName }}</h3>

        <h3> Child Component B count - {{ childCount }}</h3>
        <h3> Child Component B hero username - {{ firstName }} {{ lastName }}</h3>
    </div>
</template>

<script>
    import{inject, toRefs} from 'vue'
    export default {
        name:'ChildB',
        setup(){
            const childUserName = inject('c_userName','Default username')
            const childCount = inject('c_count',0)
            const childHero = inject('c_hero',{})

            return {
                childUserName,
                childCount,
                ...toRefs(childHero)
            }
        },
        inject: ['userName']
    }
</script>

<style scoped>

</style>