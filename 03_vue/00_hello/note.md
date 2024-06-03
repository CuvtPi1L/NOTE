# How to achieve Hello World in Vue2.0

## download vue.js from documentation
Achieve through Script tag

in index.html 
add script tag in head<script src="./vue.js">{{content}}</script>
in body add <div id="app"><div>
add <script> in body
var app = new Vue({
el:'#app',
data:{
    content:'hello world'
}

{{content}} 

setTimeout(function(){
    app.$data.content = 'bye world'
},2000)

$data is data in Vue object








