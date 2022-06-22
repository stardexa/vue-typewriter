<template>
    <div class="container fs-40" >
      <span>{{output}}</span>
      <span class="blink_me">|</span>
    </div>
</template>

<script>

export default {
  name: "App",
  data() {
    return {
      title: "Hello World",
      output: "",
      speed: "80",
      i:0,

    }
  },
  mounted() {
    this.typeWriter()
  },
  methods:{
    typeWriter(){
      if ( this.i < this.title.length) {
        this.output += this.title.charAt(this.i);
        this.i= this.i+1;
        setTimeout(this.typeWriter, this.speed);
      }else{
        setTimeout(this.writeClear,2000)
      }
    },
    writeClear(){
      this.i = 0
      this.output = ""
    }
  }
}
</script>
<style>
.fs-40{
  font-size: 40px;
}
.blink_me {
  animation: blinker 0.9s linear infinite;
}
@keyframes blinker {
  50% { opacity: 0; }
}
</style>