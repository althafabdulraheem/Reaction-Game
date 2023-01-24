 <template>
  <p id="result">{{rank}}</p>
</template>

<script>
export default {
        props:['score'],
        data()
        {
            return{
                rank:null
            }
        },
        mounted()
        {
            if(this.score<2500)
            {
                this.rank="Good"
            }
            else{
                this.rank="Bad"
            }
        }

}
</script>

<style>

</style>