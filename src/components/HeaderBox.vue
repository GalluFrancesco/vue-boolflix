<template>
    <header>
        <input type="text" v-model="searched">
        <button @click="$emit('search', searched)">Cerca</button>
    </header>
</template>

<script>
export default {

    data(){
        return{
            searched:""
        }
    }
}
</script>

<style lang="scss" scoped>

</style>