<template>
    <div id="home">
        <h2>Add a new note</h2>
        <form>
            <input type="text" id="noteinput" v-model="data" name="notein" required placeholder="Enter The Note Here"/><br/>
        </form>
        <button type="button" class="btn btn-primary" @click="add(data)">Add Note</button>
    </div>
</template>
<script>
export default {
    data:function(){
        return {data:""}
    },
    props:{
        add:{
            type:Function,
            default:function(){
                return ()=>{console.log("Default from Home")};
            }
        }
    }
}
</script>
<style scoped>
    div{
        text-align: center;
        margin:40px auto;
    }
    input{
        width:40%;
        height:50px;
        padding:5px;
    }
    button{
        margin-top:20px;
    }
</style>