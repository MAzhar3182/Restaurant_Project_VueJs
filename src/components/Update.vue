<template>
    <Header />
    <h1>Update Restaurant</h1>

</template>
<script>
import Header from "./Header.vue"
export default{
    name:"Update",
    components:{
        Header ,
    },
    mounted(){
        let user=localStorage.getItem("user-info");
        if(!user){
            this.$router.push({name:"SignUp"})
        }
    }
}

</script>
<style>
.nav{
    background-color:#333;
    overflow: hidden;
}
.nav a{
    float: left;
    color:#f2f2f2f2;
    padding:14px 16px;
    text-align: center;
    font-size:17px;
    text-decoration:none;
    margin-right:5px;
}
.nav a:hover{
    background-color:#ddd;
    color:#333;
}
</style>
