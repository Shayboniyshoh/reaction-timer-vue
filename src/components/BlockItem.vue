<template>
    <div class="block">
        <h1>Click me</h1>
    </div>
</template>

<script>
export default {
    props: ['delay'],
}
</script>

<style>
.block {
    width: 400px;
    padding: 100px 0;
    margin: 40px auto;
    border-radius: 1rem;
    text-align: center;
    color: #fff;
    background: #222;
}
</style>