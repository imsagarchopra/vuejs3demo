<template>
    <div>
        <h2>This is a Pop up</h2>
        <button @click="$emit('close','Dummy Data')"> Close Popup</button>
    </div>
</template>

<script>
    export default {
        name:'PopUp',
        emits: ['close']
    }
</script>

<style scoped>

</style>