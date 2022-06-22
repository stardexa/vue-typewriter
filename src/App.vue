<template>
  <div class="container fs-40">
    <button class="btn btn-outline-dark" @click="typeWriterText('İsminizi Giriniz.','name','30')">Name -> TypeWrite</button>
    <br>
    <span ref="name"></span>
    <span class="blink_me">|</span>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      i: 0,
    }
  },
  methods: {
    writeClear() {
      this.i = 0
      this.output = ""
    },
    typeWriterText(_title, _for, _speed = 60) {
      if (this.i < _title.length) {
        let output = '';
        output += _title.charAt(this.i);
        this.i = this.i + 1;
        this.$refs[_for].innerHTML += output
        setTimeout(() => {
          this.typeWriterText(_title, _for, _speed)
        }, _speed);
      } else {
        this.writeClear()
      }
    },
  }
}
</script>
<style>
.fs-40 {
  font-size: 40px;
}

.blink_me {
  animation: blinker 0.9s linear infinite;
}

@keyframes blinker {
  50% {
    opacity: 0;
  }
}
</style>