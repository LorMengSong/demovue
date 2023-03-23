<template>
<Child />

<h1>HTML Binding</h1>


<h1 style="color: yellow;">Home Component</h1>
<h1>Email: {{ email }}</h1>
<h1>Name: {{ name }}</h1>
<h1>Mobile: {{ mobile }}</h1>
<h1>Tax: {{ getTax("3%") }}</h1>
<div style="padding: 10px; border: 1px solid black; ">
    <h4>Technology</h4>
    <label for="java">java</label>
    <input type="checkbox" value="java" v-model="tecnology" id="java" />
    <label for="node">node</label>
    <input type="checkbox" value="node" v-model="tecnology" id="node" />
    <label for="php">php</label>
    <input type="checkbox" value="php" v-model="tecnology" id="php" />
    <label for="C#">C#</label>
    <input type="radio" value="C#" v-model="tecnology" id="C#" name="C#" />
    <h4> Technology: {{ tecnology }}</h4>

</div>
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



<form action="">
    <label for="">Email</label>
    <input type="text" name="" id="" placeholder="enter email" v-model="form.email2">
    <h2>{{ form.email2 }}</h2>
    <br><br>
    <label for="">Password</label>
    <input type="text" name="" id="" placeholder="enter password" v-model="form.password1">
    <button type="button" v-on:click="login">Login</button>
</form>

<h1>Non Prop  Data</h1>
</template>

<script>
import Child from './Child.vue';
export default {
    name: "HelloClass",
    components: {
        Child
    },
    data() {
        return {
            form:{
                email2:"",
                password1:""
            },
            name: "Test",
            email: "Hello@gmail.com",
            mobile: 2929292,
            count: " ",
            data: 0,
            email1: null,
            password: null,
            tecnology: [],
            getTax(x) {
                return x;
            }
        }
    },
    methods: {
        login(){
            console.warn(this.form);
        },
        getName() {
            alert("song is the web developer");
        },
        getCountPlus() {
            this.count = this.count + 1
        },
        getSubCount() {
            this.count = this.count - 1;
        },
        getData() {
            console.log("Email: ", this.email);
            console.log("Password: ", this.password)
        }
    }
}
</script>
