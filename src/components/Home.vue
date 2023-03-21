<template>
    <h1 style="color: yellow;">Home Component</h1>
    <h1>Email: {{ email }}</h1>
    <h1>Name: {{ name }}</h1>
    <h1>Mobile: {{ mobile }}</h1>
    <h1>Tax: {{  getTax("3%") }}</h1>
    <input type="text" name="" id="" v-model="data" />
    <input type="text" name="" id="" v-model="data" />
    
    <h1>{{ data }}</h1>
    <div style="margin: 10px;">
        <input type="text" name="" id="" placeholder="Enter email" v-model="email1">
        <input type="password" name="" id="" placeholder="Enter password" v-model="password">
    </div>
    <div>
        <h6>{{ email1 }}</h6>
        <h6>{{ password }}</h6>
    </div>
    <button type="button" v-on:click="getData()">Submit</button>

    <button v-on:click="getName()">Click Me</button>
    <button v-on:dblclick="getName()">Click Me</button>
    <button v-on:click="getCountPlus()">+</button>
    &nbsp; &nbsp;
    <span>{{ count }}</span>
    &nbsp; &nbsp;
    <button v-on:click="getSubCount()"> - </button>
</template>
<script>
    export default{
        name: "HelloClass",
        data(){
            return {
                name:"Test",
                email: "Hello@gmail.com",
                mobile: 2929292,
                count:" ",
                data:0,
                email1:null,
                password:null,
                getTax(x){
                    return x;
                }
            }
        },
        methods:{
            getName(){
                alert("song is the web developer");
            },
            getCountPlus(){
                this.count = this.count+1
            },
            getSubCount(){
                this.count = this.count-1;
            },
            getData(){
                console.log("Email: ",this.email);
                console.log("Password: ",this.password)
            }
        }
    }
</script>