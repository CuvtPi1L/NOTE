# Component 
there are two types of Component
1. Golobel Component
2. Local Component

## Globle Component
In Script tag
    Vue.component("TodoItem", {
        props:['content'],
        template:'<li>{{content}}</li>'
    })
In body Tag
<todo-item><todo-item>

!!Props needs to :[] be in array!!
### Tag!
"AaaaBbbbCccc" in init Vue.component
<aaaa-bbbb-cccc> 

### v-bind and Props:
Props passes down variables, so render into template
use v-bind:object="item" in tag
<todo-item v-bind:object="item"><todo-item>
in Vue.component("TodoItem",{
        Props:["Object"],
        template:'<li>{{Object}}</li>})

since "item" was from v-for="item in list" and list is from $data, 
it's top to bottom because "object" send to component in Props to render in template
### Template
template:"<li>{{content}}<li>"

## Local Component
I don't understand the difference
but for local component need to declare component name in scripte tag and also app Object in components

### TodoItem 
var TodoItem = {
    props: ['content']
    template:"<li>{{content}}<li>"}

### Components:
    Components:{
        TodoItem: TodoItem
    },






