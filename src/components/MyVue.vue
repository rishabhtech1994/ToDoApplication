<template>
	<div>
		<p>{{demo}}</p>
		<button v-on:click="myFunc">Click</button>
	</div>
</template>

<<script>
export default {
  name: 'HelloWorld',
  data () {
    return {
      demo:"My name is rishabh"
    }
  },
  methods:{
  	myFunc:function(){
  		alert("you have clicked me")
  	}
  }
}
</script>
