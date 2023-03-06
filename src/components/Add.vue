<template>
    <Header />
    <h1>Add Restaurant</h1>
<form class="add">
    <input type="text" v-model="restaurant.name" placeholder="Enter Name" name="name"/>
    <input type="text" v-model="restaurant.address" placeholder="Enter Address" name="address"/>
    <input type="text" v-model="restaurant.contact" placeholder="Enter Contact" name="contact"/>
    <button type="button" v-on:click="addRestaurant">Add New Restaurant</button>
</form>
</template>
<script>
import Header from "./Header.vue"
export default{
    name:"Add",
    components:{
        Header,
    },
    data(){
        return {
            restaurant:{
                name:'',
                address:'',
                contact:''
            }
        }
    },
    methods:{
addRestaurant(){
    console.warn(this.restaurant)
}
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
.add input{
    width:300px;
    height:40px;
    padding-left:20px;
    border-radius:30px;
    display: block;
    margin-bottom:30px;
    margin-left: auto;
    margin-right: auto;
    border:1px solid skyblue;
}
.add button{
    width: 320px;
    height:40px;
    border:1px solid skyblue;
    background: skyblue;
    color:#fff;
    cursor: pointer;
    border-radius: 20px;

}
</style>