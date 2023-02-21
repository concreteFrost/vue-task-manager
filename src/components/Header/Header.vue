<template>
<header class="header"><h1>{{ title }}</h1></header>
</template>

<script>
    export default{
        name: "PageHeader" ,
        props:{
            title:{
                type:String,
                default: "Task Tracker"
            }
        }      
    }
    
</script>

<style lang="scss">
@import "./Header.module.scss";
</style>