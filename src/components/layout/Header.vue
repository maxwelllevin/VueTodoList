<template>
    <header class="header">
        <h1>{{title}}</h1>
    </header>
</template>

<script>
export default {
    name: "Header",
    props: ["title"]
}
</script>

<style scoped>
.header {
    text-align: center;
    color: white;
    background: rgb(10, 202, 154);
}
</style>
