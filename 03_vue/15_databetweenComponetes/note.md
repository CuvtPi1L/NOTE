the father conponent 
use propertites(props) to transfer data to child

<counter :count="0">
<counter :count="1">

单向数据流
father can change child
child can't change data to father

clone to local veriables
      this.$emit('change', 2)?

       data: function(){
        return{
          total: 0,
        }
      },
      methods:{
        handleChange: function(step){
          alert(step)??