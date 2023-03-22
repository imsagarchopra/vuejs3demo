<template>
    <h2>Volume Tracker (0-20)</h2>
    <h3>Current Volume - {{ volume }}</h3>
    <div>
        <button @click="volume += 2">Increase</button>
        <button @click="volume -= 2">Decrease</button>
    </div>
</template>
    
<script>
export default {
    name: 'WatcherDemo',
    data() {
        return {
            volume: 0
        }
    },
    methods: {

    },
    watch:{
        volume(newValue, oldValue){
            if(newValue > oldValue && newValue === 16){
                alert("Warning - High Sound Levels");
            }
        }
    }
}
</script>
    
<style>
</style>
    