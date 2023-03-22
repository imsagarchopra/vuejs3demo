<template>
    <h2>Volume Tracker (0-20)</h2>
    <h3>Current Volume - {{ volume }}</h3>
    <div>
        <button @click="volume += 2">Increase</button>
        <button @click="volume -= 2">Decrease</button>
    </div>

    <input type="text" v-model="movie"/>
    <input type="text" v-model="movieInfo.title"/>
    <input type="text" v-model="movieInfo.actor"/>

    <button @click="movieList.push('Wonder Woman')">Add Movie</button>
</template>
    
<script>
export default {
    name: 'WatcherDemo',
    data() {
        return {
            volume: 0,
            movie:'',
            movieInfo:{
                title: '',
                actor:''
            },
            movieList: [
                'Batman', 'Superman'
            ]
        }
    },
    methods: {

    },
    watch:{
        volume(newValue, oldValue){
            if(newValue > oldValue && newValue === 16){
                alert("Warning - High Sound Levels");
            }
        },
        movie:{
            handler(newValue){
                console.log(`Calling API with movie name = ${newValue}`);
            },
            immediate: true
        },
        movieInfo:{
            handler(newValue){
                console.log(`Calling API with movie title = ${newValue.title} and actor = ${newValue.actor}`);
            },
            deep: true
        },
        movieList:{
            handler(newValue){
                console.log(`Updated list ${newValue}`);
            },
            deep: true
        }
    }
}
</script>
    
<style>
</style>
    