<template>
    <h2>{{msg}}</h2>
</template>

<script>
export default {
    // data(){
    //     return {
    //         msg:"hello vue js"
    //     }
    // }
    props:{
        msg:String
    }
}
</script>

<style>
h2 {
    color: brown
}
</style>