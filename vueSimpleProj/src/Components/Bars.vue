<template>
    <div id="bars">
        <h2>Space Used</h2>
        <div class="progress">
            <div class="progress-bar progress-bar-striped" role="progressbar" :style="returnWidth" aria-valuemax="100" aria-valuemin="0" :aria-valuenow="returnPercentage()">
                {{this.prg.toString()+"/10"}}
            </div>

        </div>
    </div>
</template>
<script>
export default {
    props:{
        prg:{
            type:Number,
            required:true,
            default:function(){
                return 1;
            }
        }
    },
    computed:{
        returnWidth(){
            return {width:this.returnPercentage()}
        }
    },
    methods:{
        returnPercentage(){
            return (this.prg*10).toString()+"%";
            
        }
    }
}
</script>
<style scoped>
div{
    text-align: center;
  }
</style>