# How to pass variable from child to father 
two thing that you can pass, 
1. variable
2. function
EventTrigger triggers function in child component 
methods under child component $emit method name and variable
method gets triggered in father compoient, finish operation chanes data,
change in data renders shits under child component

also v-bind: = :
## click triger in template
under child template:
    <li @click="function">{{content}}<li>
means trigger function when click

## function
under methods:{
    function: function (){
        this.$emit("something",this.index)}}

this will triger "something" and pass index from bottom to top

## tag @something under component html
<component-list @something="function"></component-list>
add function under father methods
methods:{
function: function(index){
    console.log("clicking child element triggered father method")}

## sending index up
since if I want to delete specfic child element, I need to key them, or id them or like give them index

from v-for 
<todo-list v-for="(item,index) in list">
two for loop, second one is specificly index
<todo-list v-for="(item,index) in list"
            v-bind:index="index"
            :content="item">

then change father method to pass index:
in methods:
    function: function(index){
        this.list.splice(index,1)














