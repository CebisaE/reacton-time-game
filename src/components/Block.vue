<template>
<div class="Block" v-if="showBlock" @click="stopTimer">
    click me
</div>

</template>

<script>
export default{
    props: ['delay'],
    data() {
        return{
            showBlock:false,
            timer:null,
            reactionTime: 0,
        }
    },
    mounted(){
        setTimeout(() =>{
            this.showBlock = true;

            this.startTimer();
        }, this.delay);
    },
    updated() {

    },
    unmounted() {
        
    },
    methods: {
        startTimer(){
            this.timer = setInterval(()=>{
                this.reactionTime += 10
            },10);
        },
        stopTimer() {
            clearInterval(this.timer);
            this.$emit('done',this.reactionTime);
        }
    },
    
}

</script>

<style>
.Block {
width: 400px; 
border-radius: 20px;
background: blueviolet;
color: white;
text-align: center;
padding: 100px 0;
margin: 40px auto;
}
</style>