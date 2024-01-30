<!-- the script is where the js code goes -->

<script setup>
import { ref } from "vue" 
//Reference variables
let user = ref("- Georges")
let text = ref("")
let updatetext = ref("")
function updateText() {
text.value += updatetext.value;
}
//Change Main Box Color 
let color = ref('Grey'); 
let newcolor = ref(''); 
// Update the mainColor with the value from the text box
function changecolor (){
    color.value = newcolor.value;
}
</script>
<!-- the template is where the html code goes -->
<template>
 <div id="navbar" class="container">  
        <div id="title">Data Management Assignment 02 {{ user }} </div>
       
</div>
<div id="flex">
        <div id="flexside">
                <div id="sidebar1" class="container"> 
                    Input:
                    <input type="text" v-model="updatetext" placeholder="Add text">
                    <button @click="updateText">Update Text</button>
                </div>
                <div id="sidebar2" class="container"> Input colour
                    <input type="text" v-model="newcolor" placeholder="Color">
                    <button @click="changecolor">Change Color</button>
                </div>
        </div>
             
                <div id="main" :style="{ backgroundColor:color }" class="container">
                    {{ text }} 
                </div>
</div>
</template>
<!-- style is where the css code goes -->
<style scoped>
html{
    
    background-color: rgb(59, 59, 59); 
    color: white;
}
body{
    margin:0;
}
div{
    /* put the borders in the inside of container */
    box-sizing: border-box;
}
#navbar{
    height: 50px;
    border-color: grey;
    background-color: white;
    color: black;
}
#flex{
    
    display: flex;
    height: calc(100vh - 50px);
}
#sidebar{
    
    width:20%;
    height:100%;
    border-color: grey;
    background-color: white;
    color: Black;
}
#main{
    width:80%;
    border-color: grey;
    background-color: white;
    color: Black;
}
#title{
    width: 70%;
    float:left;
}
.container{
    border-style: dotted;
    border-width: 1px;
}
</style>