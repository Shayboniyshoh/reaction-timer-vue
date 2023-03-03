<template>
    <p>Your reaction time: {{ this.score }} ms</p>
    <p>{{ this.rank }}</p>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            rank: null
        }
    },

    mounted() {
        if (this.score < 150) {
            this.rank = "You are a SUPER-DUPER!!!";
        } else if (this.score < 250) {
            this.rank = "You have an excellent Reaction!!!";
        } else if (this.score > 250 && this.score < 500) {
            this.rank = "You are like quick snail...:D";
        } else {
            this.rank = "Ohhh, You are Turbo...:DDD";
        }
    }
}
</script>

<style></style>