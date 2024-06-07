<tr is = "row"></tr>

data in component has to be a function()

Vue.component('row',{
  data: function(){
    return {
      content: 'this is content'
    },
    template: '<tr><td>{{content}}</tr></td>
  }
})

this.$refs.hello.innerHTML
