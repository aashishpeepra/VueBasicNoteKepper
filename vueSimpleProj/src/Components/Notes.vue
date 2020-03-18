<template>
    <div id="notes">
        <h2>Your Notes</h2>
       
             <div class="notes" v-for=" i in data.map((e,i)=>i)" :key="i" :id="i" @click="remove(i)">
            <p class="align-bottom">{{data[i]}}</p>
        </div>
       
    </div>
</template>
<script>
export default {
    props:{
        data:{
            type:Array,
            default:function(){
                return ["This is a note"]
            }
        },
        remove:{
            type:Function,
            default:function(){
                return ()=>{console.log("Default from Notes")}
            }
        }
    }
}
</script>
<style scoped>
    div{
        text-align: center;
    }
    .notes{
        font-size:120%;
        letter-spacing: 1px;
        display: inline-block;
        padding:20px 10px 2px 10px;
        line-height: 120%;
        margin:10px;
        width:250px;
        font-family: 'Shadows Into Light', cursive;
        box-shadow: 2px 2px 6px #ccc;
    }
    .notes:hover{
        background-color:#ffcccb;
        cursor: pointer;
    }
</style>