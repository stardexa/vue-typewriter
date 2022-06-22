# vue-typewrite-register

## Proje kullanım şekli
#### İlk olarak altdaki kodları projenize ekleyin 
```
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
```
<<<<<<< HEAD
#### daha sonra aşşağıdaki kullanım şekliyle kullanabilirsiniz.
=======
####daha sonra aşşağıdaki kullanım şekliyle kullanabilirsiniz.
>>>>>>> master
```
typeWriterText('İsminizi Giriniz.','name','30')
```

