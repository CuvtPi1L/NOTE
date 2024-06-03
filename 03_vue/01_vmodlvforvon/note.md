# vue doesn't contain dom methods

how to use v-for v-on v-model

# v-for 
v-for literate through items in data
<li v-for="item in list">{{item}}</li>
list as in Data elements 


# v-on 
v-on listen to DOM event 
<button v-on:click = "handleBtnClick">submit</button>

methods:{
    handelBtnClick: function(){
        alert("I'm a dog")}
}
methods in vue object init


#v-model 
connect Vue object data with dom elements
<input type='text' v-model='inputValue'>
...
data:{
    inputValue: ''
}

inputValue as Object

















