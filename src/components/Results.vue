<template>
    <p>Reaction Time -{{score}}</p>
    <p class="speed">{{speed}}</p>
</template>

<script>
export default {
    props: ['score'],
    data() {
        return {
            speed : null
        }
    },
    mounted() {
        if(this.score < 250) {
            this.speed = "Very fast"
        } 
        else if (this.score < 400) {
            this.speed = "Relatively fast"
        }
        else {
            this.speed = "Slow down there"
        }
    }
}

</script>

<style>
.speed{
font-size:1.4rem;
color:#0faf82;
font-weight: bold;

}

</style>
