<template>
    <Header />
    <h1>Hello {{name}},Welcome to home page</h1>
    <table border="2">
       
            <tr>
                <td>Id</td>
                <td>Name</td>
                <td>Contact</td>
                <td>Address</td>
            </tr>
            <tr v-for="item in restaurants" :key="item.id">
            <td>
                {{ item.id }}
            </td>
            <td>
                {{ item.name }}
            </td>
            <td>
                {{ item.contact }}
            </td>
            <td>
                {{ item.address}}
            </td>
        </tr>
    </table>
</template>
<script>
import Header from "./Header.vue"
import axios from "axios"
export default{
name:'Home',
data(){
return {
    name:'',
    restaurants:[],
}
},
components:{
    Header
},

async mounted(){
        let user=localStorage.getItem("user-info");
        this.name=JSON.parse(user).name;
        if(!user){
            this.$router.push({name:"SignUp"})
        }
        let result=await axios.get("http://localhost:3000/restaurants");
        this.restaurants=result.data;
        console.warn(result)
    }
}
</script>
<style>
table{
    margin-left: auto;
    margin-right: auto;
}
td{
    width:200px;
    height:40px;
   
}
</style>