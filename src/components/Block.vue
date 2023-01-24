<template>
    <div class="block" v-if="showBlock" @click="stop">
          Click ME!!!

    </div>
</template>

<script>

export default{
    props:['delay'],
    data(){
        return{
            showBlock:false,
            reactionTime:0,
            timer:null
        }
    },
    mounted()
    {
        // console.log("mounted")
        setTimeout(()=>{
            this.showBlock=true
            this.startTimer()
        },this.delay)
    },
    updated()
    {
         
    },
   methods:{
       startTimer()
       {
           this.timer=setInterval(()=>{
            this.reactionTime+=10
          

           },10)
       },
       stop()
       {
            clearInterval(this.timer)
            this.$emit('end',this.reactionTime)
           

       }//emit is used for emiting  custom Events or passing value from here to app.js
   }

}
</script>
<style scoped>
    .block
    {
            width: 400px;
    background: #5aefce;
    padding: 100px 0;
    border-radius: 30px;
    margin: 41px auto;
    color:white;
    font-weight: bold;
    text-align: center;
    }

</style>